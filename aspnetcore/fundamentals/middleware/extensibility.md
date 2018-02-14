---
title: "Activation d’un intergiciel (middleware) basé sur une fabrique dans ASP.NET Core"
author: guardrex
description: "Découvrez comment utiliser un middleware fortement typé avec une implémentation de l’activation basée sur une fabrique dans ASP.NET Core."
ms.author: riande
manager: wpickett
ms.custom: mvc
ms.date: 01/29/2018
ms.topic: article
ms.technology: aspnet
ms.prod: asp.net-core
uid: fundamentals/middleware/extensibility
ms.openlocfilehash: 57ff9db2edbf307f2442443dc14e69b0498f7475
ms.sourcegitcommit: f2a11a89037471a77ad68a67533754b7bb8303e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2018
---
# <a name="factory-based-middleware-activation-in-aspnet-core"></a><span data-ttu-id="ab49b-103">Activation d’un intergiciel (middleware) basé sur une fabrique dans ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ab49b-103">Factory-based middleware activation in ASP.NET Core</span></span>

<span data-ttu-id="ab49b-104">Par [Luke Latham](https://github.com/guardrex)</span><span class="sxs-lookup"><span data-stu-id="ab49b-104">By [Luke Latham](https://github.com/guardrex)</span></span>

<span data-ttu-id="ab49b-105">[IMiddlewareFactory](/dotnet/api/microsoft.aspnetcore.http.imiddlewarefactory)/[IMiddleware](/dotnet/api/microsoft.aspnetcore.http.imiddleware) est un point d’extensibilité pour l’activation d’un [middleware](xref:fundamentals/middleware/index).</span><span class="sxs-lookup"><span data-stu-id="ab49b-105">[IMiddlewareFactory](/dotnet/api/microsoft.aspnetcore.http.imiddlewarefactory)/[IMiddleware](/dotnet/api/microsoft.aspnetcore.http.imiddleware) is an extensibility point for [middleware](xref:fundamentals/middleware/index) activation.</span></span>

<span data-ttu-id="ab49b-106">Les méthodes d’extension de `UseMiddleware` vérifient si le type inscrit d’un middleware implémente `IMiddleware`.</span><span class="sxs-lookup"><span data-stu-id="ab49b-106">`UseMiddleware` extension methods check if a middleware's registered type implements `IMiddleware`.</span></span> <span data-ttu-id="ab49b-107">Si c’est le cas, l’instance de `IMiddlewareFactory` inscrite dans le conteneur est utilisée pour résoudre l’implémentation de `IMiddleware`, au lieu de la logique d’activation de middleware basée sur une convention.</span><span class="sxs-lookup"><span data-stu-id="ab49b-107">If it does, the `IMiddlewareFactory` instance registered in the container is used to resolve the `IMiddleware` implementation instead of using the convention-based middleware activation logic.</span></span> <span data-ttu-id="ab49b-108">Le middleware est inscrit comme service délimité ou temporaire dans le conteneur de service de l’application.</span><span class="sxs-lookup"><span data-stu-id="ab49b-108">The middleware is registered as a scoped or transient service in the app's service container.</span></span>

<span data-ttu-id="ab49b-109">Avantages :</span><span class="sxs-lookup"><span data-stu-id="ab49b-109">Benefits:</span></span>

* <span data-ttu-id="ab49b-110">Activation par demande (injection de services délimités)</span><span class="sxs-lookup"><span data-stu-id="ab49b-110">Activation per request (injection of scoped services)</span></span>
* <span data-ttu-id="ab49b-111">Typage fort du middleware</span><span class="sxs-lookup"><span data-stu-id="ab49b-111">Strong typing of middleware</span></span>

<span data-ttu-id="ab49b-112">`IMiddleware` est activé par demande : des services délimités peuvent ainsi être injectés dans le constructeur du middleware.</span><span class="sxs-lookup"><span data-stu-id="ab49b-112">`IMiddleware` is activated per request, so scoped services can be injected into the middleware's constructor.</span></span>

<span data-ttu-id="ab49b-113">[Affichez ou téléchargez l’exemple de code](https://github.com/aspnet/Docs/tree/master/aspnetcore/fundamentals/middleware/extensibility/sample) ([procédure de téléchargement](xref:tutorials/index#how-to-download-a-sample))</span><span class="sxs-lookup"><span data-stu-id="ab49b-113">[View or download sample code](https://github.com/aspnet/Docs/tree/master/aspnetcore/fundamentals/middleware/extensibility/sample) ([how to download](xref:tutorials/index#how-to-download-a-sample))</span></span>

<span data-ttu-id="ab49b-114">L’exemple d’application montre un middleware activé par :</span><span class="sxs-lookup"><span data-stu-id="ab49b-114">The sample app demonstrates middleware activated by:</span></span>

* <span data-ttu-id="ab49b-115">Convention (`ConventionalMiddleware`).</span><span class="sxs-lookup"><span data-stu-id="ab49b-115">Convention (`ConventionalMiddleware`).</span></span> <span data-ttu-id="ab49b-116">Pour plus d’informations sur l’activation conventionnelle de middleware, consultez la rubrique [Intergiciel (middleware)](xref:fundamentals/middleware/index).</span><span class="sxs-lookup"><span data-stu-id="ab49b-116">For more information on conventional middleware activation, see the [Middleware](xref:fundamentals/middleware/index) topic.</span></span>
* <span data-ttu-id="ab49b-117">Une implémentation de [IMiddlewareFactory](/dotnet/api/microsoft.aspnetcore.http.imiddlewarefactory) (`IMiddlewareMiddleware`).</span><span class="sxs-lookup"><span data-stu-id="ab49b-117">An [IMiddlewareFactory](/dotnet/api/microsoft.aspnetcore.http.imiddlewarefactory) implementation (`IMiddlewareMiddleware`).</span></span> <span data-ttu-id="ab49b-118">La [classe MiddlewareFactory](/dotnet/api/microsoft.aspnetcore.http.middlewarefactory) par défaut active le middleware.</span><span class="sxs-lookup"><span data-stu-id="ab49b-118">The default [MiddlewareFactory class](/dotnet/api/microsoft.aspnetcore.http.middlewarefactory) activates the middleware.</span></span>

<span data-ttu-id="ab49b-119">Les implémentations de middleware fonctionnent de façon identique et enregistrent la valeur fournie par un paramètre de la chaîne de requête (`key`).</span><span class="sxs-lookup"><span data-stu-id="ab49b-119">The middleware implementations function identically and record the value provided by a query string parameter (`key`).</span></span> <span data-ttu-id="ab49b-120">Les middlewares utilisent un contexte de base de données injecté (un service délimité) pour enregistrer la valeur de la chaîne de requête dans une base de données en mémoire.</span><span class="sxs-lookup"><span data-stu-id="ab49b-120">The middlewares use an injected database context (a scoped service) to record the query string value in an in-memory database.</span></span>

## <a name="imiddleware"></a><span data-ttu-id="ab49b-121">IMiddleware</span><span class="sxs-lookup"><span data-stu-id="ab49b-121">IMiddleware</span></span>

<span data-ttu-id="ab49b-122">[IMiddleware](/dotnet/api/microsoft.aspnetcore.http.imiddleware) définit l’intergiciel pour le pipeline des requêtes de l’application.</span><span class="sxs-lookup"><span data-stu-id="ab49b-122">[IMiddleware](/dotnet/api/microsoft.aspnetcore.http.imiddleware) defines middleware for the app's request pipeline.</span></span> <span data-ttu-id="ab49b-123">La méthode [InvokeAsync(HttpContext, RequestDelegate)](/dotnet/api/microsoft.aspnetcore.http.imiddleware.invokeasync#Microsoft_AspNetCore_Http_IMiddleware_InvokeAsync_Microsoft_AspNetCore_Http_HttpContext_Microsoft_AspNetCore_Http_RequestDelegate_) gère les requêtes et retourne un élément `Task` qui représente l’exécution du middleware.</span><span class="sxs-lookup"><span data-stu-id="ab49b-123">The [InvokeAsync(HttpContext, RequestDelegate)](/dotnet/api/microsoft.aspnetcore.http.imiddleware.invokeasync#Microsoft_AspNetCore_Http_IMiddleware_InvokeAsync_Microsoft_AspNetCore_Http_HttpContext_Microsoft_AspNetCore_Http_RequestDelegate_) method handles requests and returns a `Task` that represents the execution of the middleware.</span></span>

<span data-ttu-id="ab49b-124">Middleware activé par convention :</span><span class="sxs-lookup"><span data-stu-id="ab49b-124">Middleware activated by convention:</span></span>

[!code-csharp[Main](extensibility/sample/Middleware/ConventionalMiddleware.cs?name=snippet1)]

<span data-ttu-id="ab49b-125">Middleware activé par `MiddlewareFactory` :</span><span class="sxs-lookup"><span data-stu-id="ab49b-125">Middleware activated by `MiddlewareFactory`:</span></span>

[!code-csharp[Main](extensibility/sample/Middleware/IMiddlewareMiddleware.cs?name=snippet1)]

<span data-ttu-id="ab49b-126">Des extensions sont créées pour les middleware :</span><span class="sxs-lookup"><span data-stu-id="ab49b-126">Extensions are created for the middlewares:</span></span>

[!code-csharp[Main](extensibility/sample/Middleware/MiddlewareExtensions.cs?name=snippet1)]

<span data-ttu-id="ab49b-127">Il n’est pas possible de passer des objets au middleware activé par fabrique avec `UseMiddleware` :</span><span class="sxs-lookup"><span data-stu-id="ab49b-127">It isn't possible to pass objects to the factory-activated middleware with `UseMiddleware`:</span></span>

```csharp
public static IApplicationBuilder UseIMiddlewareMiddleware(
    this IApplicationBuilder builder, bool option)
{
    // Passing 'option' as an argument throws a NotSupportedException at runtime.
    return builder.UseMiddleware<IMiddlewareMiddleware>(option);
}
```

<span data-ttu-id="ab49b-128">Le middleware activé par fabrique est ajouté au conteneur intégré dans *Startup.cs* :</span><span class="sxs-lookup"><span data-stu-id="ab49b-128">The factory-activated middleware is added to the built-in container in *Startup.cs*:</span></span>

[!code-csharp[Main](extensibility/sample/Startup.cs?name=snippet1&highlight=6)]

<span data-ttu-id="ab49b-129">Les deux middlewares sont inscrits dans le pipeline de traitement des requêtes dans `Configure` :</span><span class="sxs-lookup"><span data-stu-id="ab49b-129">Both middlewares are registered in the request processing pipeline in `Configure`:</span></span>

[!code-csharp[Main](extensibility/sample/Startup.cs?name=snippet2&highlight=12-13)]

## <a name="imiddlewarefactory"></a><span data-ttu-id="ab49b-130">IMiddlewareFactory</span><span class="sxs-lookup"><span data-stu-id="ab49b-130">IMiddlewareFactory</span></span>

<span data-ttu-id="ab49b-131">[IMiddlewareFactory](/dotnet/api/microsoft.aspnetcore.http.imiddlewarefactory) fournit des méthodes pour créer un middleware.</span><span class="sxs-lookup"><span data-stu-id="ab49b-131">[IMiddlewareFactory](/dotnet/api/microsoft.aspnetcore.http.imiddlewarefactory) provides methods to create middleware.</span></span> <span data-ttu-id="ab49b-132">L’implémentation de la fabrique de middlewares est inscrite dans le conteneur comme service délimité.</span><span class="sxs-lookup"><span data-stu-id="ab49b-132">The middleware factory implementation is registered in the container as a scoped service.</span></span>

<span data-ttu-id="ab49b-133">L’implémentation par défaut de `IMiddlewareFactory`, [MiddlewareFactory](/dotnet/api/microsoft.aspnetcore.http.middlewarefactory), se trouve dans le package [Microsoft.AspNetCore.Http](https://www.nuget.org/packages/Microsoft.AspNetCore.Http/) ([source de référence](https://github.com/aspnet/HttpAbstractions/blob/release/2.0/src/Microsoft.AspNetCore.Http/MiddlewareFactory.cs)).</span><span class="sxs-lookup"><span data-stu-id="ab49b-133">The default `IMiddlewareFactory` implementation, [MiddlewareFactory](/dotnet/api/microsoft.aspnetcore.http.middlewarefactory), is found in the [Microsoft.AspNetCore.Http](https://www.nuget.org/packages/Microsoft.AspNetCore.Http/) package ([reference source](https://github.com/aspnet/HttpAbstractions/blob/release/2.0/src/Microsoft.AspNetCore.Http/MiddlewareFactory.cs)).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ab49b-134">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ab49b-134">Additional resources</span></span>

* [<span data-ttu-id="ab49b-135">Intergiciel (middleware)</span><span class="sxs-lookup"><span data-stu-id="ab49b-135">Middleware</span></span>](xref:fundamentals/middleware/index)