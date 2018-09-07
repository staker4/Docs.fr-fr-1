---
title: Nouveautés d’ASP.NET Core 2.0
author: rick-anderson
description: Découvrez les nouvelles fonctionnalités d’ASP.NET Core 2.0.
monikerRange: = aspnetcore-2.0
ms.author: riande
ms.date: 07/10/2017
uid: aspnetcore-2.0
ms.openlocfilehash: df5a394c8512a99c706573fd27877e4cdd2eb7df
ms.sourcegitcommit: d27317c16f113e7c111583042ec7e4c5a26adf6f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2018
ms.locfileid: "42909002"
---
# <a name="whats-new-in-aspnet-core-20"></a><span data-ttu-id="19ea5-103">Nouveautés d’ASP.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="19ea5-103">What's new in ASP.NET Core 2.0</span></span>

<span data-ttu-id="19ea5-104">Cet article met en évidence les modifications les plus importantes dans ASP.NET 2.0 Core et fournit des liens vers la documentation appropriée.</span><span class="sxs-lookup"><span data-stu-id="19ea5-104">This article highlights the most significant changes in ASP.NET Core 2.0, with links to relevant documentation.</span></span>

## <a name="razor-pages"></a><span data-ttu-id="19ea5-105">Pages Razor</span><span class="sxs-lookup"><span data-stu-id="19ea5-105">Razor Pages</span></span>

<span data-ttu-id="19ea5-106">Les pages Razor sont une nouvelle fonctionnalité d’ASP.NET Core MVC qui permet de développer des scénarios orientés page de façon plus simple et plus productive.</span><span class="sxs-lookup"><span data-stu-id="19ea5-106">Razor Pages is a new feature of ASP.NET Core MVC that makes coding page-focused scenarios easier and more productive.</span></span>

<span data-ttu-id="19ea5-107">Pour plus d’informations, consultez l’introduction et le didacticiel :</span><span class="sxs-lookup"><span data-stu-id="19ea5-107">For more information, see the introduction and tutorial:</span></span>

* [<span data-ttu-id="19ea5-108">Présentation des pages Razor</span><span class="sxs-lookup"><span data-stu-id="19ea5-108">Introduction to Razor Pages</span></span>](xref:razor-pages/index)
* [<span data-ttu-id="19ea5-109">Bien démarrer avec les pages Razor</span><span class="sxs-lookup"><span data-stu-id="19ea5-109">Get started with Razor Pages</span></span>](xref:tutorials/razor-pages/razor-pages-start)

## <a name="aspnet-core-metapackage"></a><span data-ttu-id="19ea5-110">Métapackage ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="19ea5-110">ASP.NET Core metapackage</span></span>

<span data-ttu-id="19ea5-111">Un nouveau métapackage ASP.NET Core comprend tous les packages créés et pris en charge par les équipes ASP.NET Core et Entity Framework Core, ainsi que leurs dépendances internes et tierces.</span><span class="sxs-lookup"><span data-stu-id="19ea5-111">A new ASP.NET Core metapackage includes all of the packages made and supported by the ASP.NET Core and Entity Framework Core teams, along with their internal and 3rd-party dependencies.</span></span> <span data-ttu-id="19ea5-112">Vous n’avez plus besoin de choisir des fonctionnalités ASP.NET Core individuelles par package.</span><span class="sxs-lookup"><span data-stu-id="19ea5-112">You no longer need to choose individual ASP.NET Core features by package.</span></span> <span data-ttu-id="19ea5-113">Toutes les fonctionnalités sont incluses dans le package [Microsoft.AspNetCore.All](https://www.nuget.org/packages/Microsoft.AspNetCore.All).</span><span class="sxs-lookup"><span data-stu-id="19ea5-113">All features are included in the [Microsoft.AspNetCore.All](https://www.nuget.org/packages/Microsoft.AspNetCore.All) package.</span></span> <span data-ttu-id="19ea5-114">Les modèles par défaut utilisent ce package.</span><span class="sxs-lookup"><span data-stu-id="19ea5-114">The default templates use this package.</span></span>

<span data-ttu-id="19ea5-115">Pour plus d’informations, consultez [Métapackage Microsoft.AspNetCore.All pour ASP.NET Core 2.0](xref:fundamentals/metapackage).</span><span class="sxs-lookup"><span data-stu-id="19ea5-115">For more information, see [Microsoft.AspNetCore.All metapackage for ASP.NET Core 2.0](xref:fundamentals/metapackage).</span></span>

## <a name="runtime-store"></a><span data-ttu-id="19ea5-116">Magasin Runtime</span><span class="sxs-lookup"><span data-stu-id="19ea5-116">Runtime Store</span></span>

<span data-ttu-id="19ea5-117">Les applications qui utilisent le métapackage `Microsoft.AspNetCore.All` tirent automatiquement parti du nouveau magasin Runtime de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="19ea5-117">Applications that use the `Microsoft.AspNetCore.All` metapackage automatically take advantage of the new .NET Core Runtime Store.</span></span> <span data-ttu-id="19ea5-118">Ce magasin contient toutes les ressources Runtime nécessaires à l’exécution des applications ASP.NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="19ea5-118">The Store contains all the runtime assets needed to run ASP.NET Core 2.0 applications.</span></span> <span data-ttu-id="19ea5-119">Quand vous utilisez le métapackage `Microsoft.AspNetCore.All`, aucune des ressources des packages NuGet ASP.NET Core référencés ne sont déployées avec l’application, car elles se trouvent déjà sur le système cible.</span><span class="sxs-lookup"><span data-stu-id="19ea5-119">When you use the `Microsoft.AspNetCore.All` metapackage, no assets from the referenced ASP.NET Core NuGet packages are deployed with the application because they already reside on the target system.</span></span> <span data-ttu-id="19ea5-120">Les ressources dans le magasin Runtime sont également précompilées afin d’améliorer la vitesse de démarrage des applications.</span><span class="sxs-lookup"><span data-stu-id="19ea5-120">The assets in the Runtime Store are also precompiled to improve application startup time.</span></span>

<span data-ttu-id="19ea5-121">Pour plus d’informations, consultez [Magasin de packages Runtime](/dotnet/core/deploying/runtime-store)</span><span class="sxs-lookup"><span data-stu-id="19ea5-121">For more information, see [Runtime store](/dotnet/core/deploying/runtime-store)</span></span>

## <a name="net-standard-20"></a><span data-ttu-id="19ea5-122">.NET Standard 2.0</span><span class="sxs-lookup"><span data-stu-id="19ea5-122">.NET Standard 2.0</span></span>

<span data-ttu-id="19ea5-123">Les packages ASP.NET Core 2.0 ciblent .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="19ea5-123">The ASP.NET Core 2.0 packages target .NET Standard 2.0.</span></span> <span data-ttu-id="19ea5-124">Les packages peuvent être référencés par d’autres bibliothèques .NET Standard 2.0, et ils peuvent s’exécuter sur des implémentations de .NET conformes à .NET Standard 2.0, notamment .NET Core 2.0 et le .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="19ea5-124">The packages can be referenced by other .NET Standard 2.0 libraries, and they can run on .NET Standard 2.0-compliant implementations of .NET, including .NET Core 2.0 and .NET Framework 4.6.1.</span></span> 

<span data-ttu-id="19ea5-125">Le métapackage `Microsoft.AspNetCore.All` cible .NET Core 2.0 uniquement, car il est destiné à être utilisé avec .NET Core 2.0 Runtime Store.</span><span class="sxs-lookup"><span data-stu-id="19ea5-125">The `Microsoft.AspNetCore.All` metapackage targets .NET Core 2.0 only, because it's intended to be used with the .NET Core 2.0 Runtime Store.</span></span>

## <a name="configuration-update"></a><span data-ttu-id="19ea5-126">Mise à jour de la configuration</span><span class="sxs-lookup"><span data-stu-id="19ea5-126">Configuration update</span></span>

<span data-ttu-id="19ea5-127">Une instance de `IConfiguration` est ajoutée au conteneur de services par défaut dans ASP.NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="19ea5-127">An `IConfiguration` instance is added to the services container by default in ASP.NET Core 2.0.</span></span> <span data-ttu-id="19ea5-128">Quand `IConfiguration` est dans le conteneur de services, il est plus facile pour les applications de récupérer des valeurs de configuration à partir du conteneur.</span><span class="sxs-lookup"><span data-stu-id="19ea5-128">`IConfiguration` in the services container makes it easier for applications to retrieve configuration values from the container.</span></span>

<span data-ttu-id="19ea5-129">Pour plus d’informations sur l’état de la documentation planifiée, consultez le [problème GitHub](https://github.com/aspnet/Docs/issues/3387).</span><span class="sxs-lookup"><span data-stu-id="19ea5-129">For information about the status of planned documentation, see the [GitHub issue](https://github.com/aspnet/Docs/issues/3387).</span></span>

## <a name="logging-update"></a><span data-ttu-id="19ea5-130">Mise à jour de la journalisation</span><span class="sxs-lookup"><span data-stu-id="19ea5-130">Logging update</span></span>

<span data-ttu-id="19ea5-131">Dans ASP.NET Core 2.0, la journalisation est incorporée dans le système d’injection de dépendance par défaut.</span><span class="sxs-lookup"><span data-stu-id="19ea5-131">In ASP.NET Core 2.0, logging is incorporated into the dependency injection (DI) system by default.</span></span> <span data-ttu-id="19ea5-132">Vous pouvez ajouter des fournisseurs et configurer le filtrage dans le fichier *Program.cs* plutôt que dans le fichier *Startup.cs*.</span><span class="sxs-lookup"><span data-stu-id="19ea5-132">You add providers and configure filtering in the *Program.cs* file instead of in the *Startup.cs* file.</span></span> <span data-ttu-id="19ea5-133">De plus, le `ILoggerFactory` par défaut prend en charge le filtrage d’une manière qui vous permet d’adopter une approche flexible pour le filtrage entre fournisseurs et le filtrage propre au fournisseur.</span><span class="sxs-lookup"><span data-stu-id="19ea5-133">And the default `ILoggerFactory` supports filtering in a way that lets you use one flexible approach for both cross-provider filtering and specific-provider filtering.</span></span>

<span data-ttu-id="19ea5-134">Pour plus d’informations, consultez [Introduction à la journalisation](xref:fundamentals/logging/index).</span><span class="sxs-lookup"><span data-stu-id="19ea5-134">For more information, see [Introduction to Logging](xref:fundamentals/logging/index).</span></span>

## <a name="authentication-update"></a><span data-ttu-id="19ea5-135">Mise à jour de l’authentification</span><span class="sxs-lookup"><span data-stu-id="19ea5-135">Authentication update</span></span>

<span data-ttu-id="19ea5-136">Un nouveau modèle d’authentification simplifie la configuration de l’authentification pour une application à l’aide de l’injection de dépendance.</span><span class="sxs-lookup"><span data-stu-id="19ea5-136">A new authentication model makes it easier to configure authentication for an application using DI.</span></span>

<span data-ttu-id="19ea5-137">De nouveaux modèles sont disponibles pour configurer l’authentification pour les applications web et les API web à l’aide de [Azure AD B2C] (https://azure.microsoft.com/services/active-directory-b2c/).</span><span class="sxs-lookup"><span data-stu-id="19ea5-137">New templates are available for configuring authentication for web apps and web APIs using [Azure AD B2C] (https://azure.microsoft.com/services/active-directory-b2c/).</span></span>

<span data-ttu-id="19ea5-138">Pour plus d’informations sur l’état de la documentation planifiée, consultez le [problème GitHub](https://github.com/aspnet/Docs/issues/3054).</span><span class="sxs-lookup"><span data-stu-id="19ea5-138">For information about the status of planned documentation, see the [GitHub issue](https://github.com/aspnet/Docs/issues/3054).</span></span>

## <a name="identity-update"></a><span data-ttu-id="19ea5-139">Mise à jour d’Identity</span><span class="sxs-lookup"><span data-stu-id="19ea5-139">Identity update</span></span>

<span data-ttu-id="19ea5-140">Nous avons simplifié la génération d’API web sécurisées à l’aide d’Identity dans ASP.NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="19ea5-140">We've made it easier to build secure web APIs using Identity in ASP.NET Core 2.0.</span></span> <span data-ttu-id="19ea5-141">Vous pouvez acquérir des jetons d’accès pour accéder à vos API web à l’aide de la [bibliothèque d’authentification Microsoft (MSAL, Microsoft Authentication Library)](https://www.nuget.org/packages/Microsoft.Identity.Client).</span><span class="sxs-lookup"><span data-stu-id="19ea5-141">You can acquire access tokens for accessing your web APIs using the [Microsoft Authentication Library (MSAL)](https://www.nuget.org/packages/Microsoft.Identity.Client).</span></span>

<span data-ttu-id="19ea5-142">Pour plus d’informations sur les modifications apportées à l’authentification dans la version 2.0, consultez les ressources suivantes :</span><span class="sxs-lookup"><span data-stu-id="19ea5-142">For more information on authentication changes in 2.0, see the following resources:</span></span>

* [<span data-ttu-id="19ea5-143">Account confirmation and password recovery in ASP.NET Core (Confirmation de compte et récupération de mot de passe dans ASP.NET Core)</span><span class="sxs-lookup"><span data-stu-id="19ea5-143">Account confirmation and password recovery in ASP.NET Core</span></span>](xref:security/authentication/accconfirm)
* [<span data-ttu-id="19ea5-144">Activer la génération de code QR pour les applications d’authentification dans ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="19ea5-144">Enable QR Code generation for authenticator apps in ASP.NET Core</span></span>](xref:security/authentication/identity-enable-qrcodes)
* [<span data-ttu-id="19ea5-145">Migrer l’authentification et l’identité vers ASP.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="19ea5-145">Migrate Authentication and Identity to ASP.NET Core 2.0</span></span>](xref:migration/1x-to-2x/identity-2x)

## <a name="spa-templates"></a><span data-ttu-id="19ea5-146">Modèles SPA</span><span class="sxs-lookup"><span data-stu-id="19ea5-146">SPA templates</span></span>

<span data-ttu-id="19ea5-147">Des modèles de projet SPA (Single Page Application) pour Angular, Aurelia, Knockout.js, React.js et React.js avec Redux sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="19ea5-147">Single Page Application (SPA) project templates for Angular, Aurelia, Knockout.js, React.js, and React.js with Redux are available.</span></span> <span data-ttu-id="19ea5-148">Le modèle Angular a été mis à jour vers Angular 4.</span><span class="sxs-lookup"><span data-stu-id="19ea5-148">The Angular template has been updated to Angular 4.</span></span> <span data-ttu-id="19ea5-149">Les modèles Angular et React sont disponibles par défaut. Pour plus d’informations sur l’obtention des autres modèles, consultez [Créer un projet SPA](xref:client-side/spa-services#creating-a-new-project).</span><span class="sxs-lookup"><span data-stu-id="19ea5-149">The Angular and React templates are available by default; for information about how to get the other templates, see [Create a new SPA project](xref:client-side/spa-services#creating-a-new-project).</span></span> <span data-ttu-id="19ea5-150">Pour plus d’informations sur la génération d’un projet SPA dans ASP.NET Core, consultez [Utiliser JavaScriptServices pour créer des applications web monopages](xref:client-side/spa-services).</span><span class="sxs-lookup"><span data-stu-id="19ea5-150">For information about how to build a SPA in ASP.NET Core, see [Use JavaScriptServices for Creating Single Page Applications](xref:client-side/spa-services).</span></span>

## <a name="kestrel-improvements"></a><span data-ttu-id="19ea5-151">Améliorations apportées à Kestrel</span><span class="sxs-lookup"><span data-stu-id="19ea5-151">Kestrel improvements</span></span>

<span data-ttu-id="19ea5-152">Le serveur web Kestrel offre de nouvelles fonctionnalités qui le rendent plus adapté en tant que serveur connecté à Internet.</span><span class="sxs-lookup"><span data-stu-id="19ea5-152">The Kestrel web server has new features that make it more suitable as an Internet-facing server.</span></span> <span data-ttu-id="19ea5-153">Plusieurs options de configuration de contrainte de serveur ont été ajoutées à la nouvelle propriété `Limits` de la classe `KestrelServerOptions`.</span><span class="sxs-lookup"><span data-stu-id="19ea5-153">A number of server constraint configuration options are added in the `KestrelServerOptions` class's new `Limits` property.</span></span> <span data-ttu-id="19ea5-154">Ajoutez des limites pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="19ea5-154">Add limits for the following:</span></span>

- <span data-ttu-id="19ea5-155">Nombre maximale de connexions client</span><span class="sxs-lookup"><span data-stu-id="19ea5-155">Maximum client connections</span></span>
- <span data-ttu-id="19ea5-156">Taille maximale du corps de la requête</span><span class="sxs-lookup"><span data-stu-id="19ea5-156">Maximum request body size</span></span>
- <span data-ttu-id="19ea5-157">Débit données minimal du corps de la requête</span><span class="sxs-lookup"><span data-stu-id="19ea5-157">Minimum request body data rate</span></span>

<span data-ttu-id="19ea5-158">Pour plus d’informations, consultez [Implémentation du serveur web Kestrel dans ASP.NET Core](xref:fundamentals/servers/kestrel).</span><span class="sxs-lookup"><span data-stu-id="19ea5-158">For more information, see [Kestrel web server implementation in ASP.NET Core](xref:fundamentals/servers/kestrel).</span></span>

## <a name="weblistener-renamed-to-httpsys"></a><span data-ttu-id="19ea5-159">WebListener a été renommé HTTP.sys</span><span class="sxs-lookup"><span data-stu-id="19ea5-159">WebListener renamed to HTTP.sys</span></span>

<span data-ttu-id="19ea5-160">Les packages `Microsoft.AspNetCore.Server.WebListener` et `Microsoft.Net.Http.Server` ont été fusionnés dans un nouveau package `Microsoft.AspNetCore.Server.HttpSys`.</span><span class="sxs-lookup"><span data-stu-id="19ea5-160">The packages `Microsoft.AspNetCore.Server.WebListener` and `Microsoft.Net.Http.Server` have been merged into a new package `Microsoft.AspNetCore.Server.HttpSys`.</span></span> <span data-ttu-id="19ea5-161">Les espaces de noms ont été mis à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="19ea5-161">The namespaces have been updated to match.</span></span>

<span data-ttu-id="19ea5-162">Pour plus d’informations, consultez [Implémentation du serveur web HTTP.sys dans ASP.NET Core](xref:fundamentals/servers/httpsys).</span><span class="sxs-lookup"><span data-stu-id="19ea5-162">For more information, see [HTTP.sys web server implementation in ASP.NET Core](xref:fundamentals/servers/httpsys).</span></span>

## <a name="enhanced-http-header-support"></a><span data-ttu-id="19ea5-163">Prise en charge améliorée de l’en-tête HTTP</span><span class="sxs-lookup"><span data-stu-id="19ea5-163">Enhanced HTTP header support</span></span>

<span data-ttu-id="19ea5-164">Lors de l’utilisation de MVC pour transmettre un `FileStreamResult` ou un `FileContentResult`, vous pouvez maintenant définir un `ETag` ou une date `LastModified` sur le contenu que vous transmettez.</span><span class="sxs-lookup"><span data-stu-id="19ea5-164">When using MVC to transmit a `FileStreamResult` or a `FileContentResult`, you now have the option to set an `ETag` or a `LastModified` date on the content you transmit.</span></span> <span data-ttu-id="19ea5-165">Vous pouvez définir ces valeurs sur le contenu retourné avec du code semblable au suivant :</span><span class="sxs-lookup"><span data-stu-id="19ea5-165">You can set these values on the returned content with code similar to the following:</span></span>

```csharp
var data = Encoding.UTF8.GetBytes("This is a sample text from a binary array");
var entityTag = new EntityTagHeaderValue("\"MyCalculatedEtagValue\"");
return File(data, "text/plain", "downloadName.txt", lastModified: DateTime.UtcNow.AddSeconds(-5), entityTag: entityTag);
```

<span data-ttu-id="19ea5-166">Le fichier retourné aux visiteurs sera décoré avec les en-têtes HTTP appropriés pour les valeurs `ETag` et `LastModified`.</span><span class="sxs-lookup"><span data-stu-id="19ea5-166">The file returned to your visitors will be decorated with the appropriate HTTP headers for the `ETag` and `LastModified` values.</span></span>

<span data-ttu-id="19ea5-167">Si un visiteur de l’application demande du contenu avec un en-tête de requête de plage, ASP.NET Core reconnaît la requête et gère l’en-tête.</span><span class="sxs-lookup"><span data-stu-id="19ea5-167">If an application visitor requests content with a Range Request header, ASP.NET Core recognizes the request and handles the header.</span></span> <span data-ttu-id="19ea5-168">Si le contenu demandé peut être remis partiellement, ASP.NET Core retourne uniquement le jeu d’octets demandé.</span><span class="sxs-lookup"><span data-stu-id="19ea5-168">If the requested content can be partially delivered, ASP.NET Core appropriately skips and returns just the requested set of bytes.</span></span> <span data-ttu-id="19ea5-169">Vous n’avez pas besoin d’écrire des gestionnaires spéciaux dans vos méthodes pour adapter ou gérer cette fonctionnalité. Elle est gérée automatiquement pour vous.</span><span class="sxs-lookup"><span data-stu-id="19ea5-169">You don't need to write any special handlers into your methods to adapt or handle this feature; it's automatically handled for you.</span></span>

## <a name="hosting-startup-and-application-insights"></a><span data-ttu-id="19ea5-170">Hébergement du démarrage et Application Insights</span><span class="sxs-lookup"><span data-stu-id="19ea5-170">Hosting startup and Application Insights</span></span>

<span data-ttu-id="19ea5-171">Les environnements d’hébergement peuvent désormais injecter des dépendances de packages supplémentaires et exécuter du code pendant le démarrage de l’application, sans que celle-ci doive explicitement prendre une dépendance ou appeler des méthodes.</span><span class="sxs-lookup"><span data-stu-id="19ea5-171">Hosting environments can now inject extra package dependencies and execute code during application startup, without the application needing to explicitly take a dependency or call any methods.</span></span> <span data-ttu-id="19ea5-172">Vous pouvez utiliser cette fonctionnalité pour permettre à certains environnements de « déclencher » des fonctionnalités qui leur sont uniques, sans que l’application ait besoin de savoir à l’avance.</span><span class="sxs-lookup"><span data-stu-id="19ea5-172">This feature can be used to enable certain environments to "light-up" features unique to that environment without the application needing to know ahead of time.</span></span> 

<span data-ttu-id="19ea5-173">Dans ASP.NET Core 2.0, cette fonctionnalité est utilisée pour activer automatiquement les diagnostics Application Insights lors du débogage dans Visual Studio et (après vous être inscrit) lors de l’exécution dans Azure App Services.</span><span class="sxs-lookup"><span data-stu-id="19ea5-173">In ASP.NET Core 2.0, this feature is used to automatically enable Application Insights diagnostics when debugging in Visual Studio and (after opting in) when running in Azure App Services.</span></span> <span data-ttu-id="19ea5-174">Par conséquent, les modèles de projet n’ajoutent plus de code et de packages Application Insights par défaut.</span><span class="sxs-lookup"><span data-stu-id="19ea5-174">As a result, the project templates no longer add Application Insights packages and code by default.</span></span>

<span data-ttu-id="19ea5-175">Pour plus d’informations sur l’état de la documentation planifiée, consultez le [problème GitHub](https://github.com/aspnet/Docs/issues/3389).</span><span class="sxs-lookup"><span data-stu-id="19ea5-175">For information about the status of planned documentation, see the [GitHub issue](https://github.com/aspnet/Docs/issues/3389).</span></span>

## <a name="automatic-use-of-anti-forgery-tokens"></a><span data-ttu-id="19ea5-176">Utilisation automatique des jetons anti-contrefaçon</span><span class="sxs-lookup"><span data-stu-id="19ea5-176">Automatic use of anti-forgery tokens</span></span>

<span data-ttu-id="19ea5-177">ASP.NET Core a toujours facilité l’encodage HTML du contenu par défaut, mais la nouvelle version aide encore davantage à prévenir les attaques par falsification de requête intersites (XSRF).</span><span class="sxs-lookup"><span data-stu-id="19ea5-177">ASP.NET Core has always helped HTML-encode content by default, but with the new version an extra step is taken to help prevent cross-site request forgery (XSRF) attacks.</span></span> <span data-ttu-id="19ea5-178">ASP.NET Core émet désormais des jetons anti-contrefaçon par défaut, et les valide sur les pages et les actions POST de formulaire sans configuration supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="19ea5-178">ASP.NET Core will now emit anti-forgery tokens by default and validate them on form POST actions and pages without extra configuration.</span></span>

<span data-ttu-id="19ea5-179">Pour plus d’informations, consultez [Empêcher les attaques par falsification de requête intersites (XSRF/CSRF)](xref:security/anti-request-forgery).</span><span class="sxs-lookup"><span data-stu-id="19ea5-179">For more information, see [Prevent Cross-Site Request Forgery (XSRF/CSRF) attacks](xref:security/anti-request-forgery).</span></span>

## <a name="automatic-precompilation"></a><span data-ttu-id="19ea5-180">Précompilation automatique</span><span class="sxs-lookup"><span data-stu-id="19ea5-180">Automatic precompilation</span></span>

<span data-ttu-id="19ea5-181">La précompilation de vue Razor est activée par défaut pendant la publication, ce qui réduit la taille de sortie de publication et la durée de démarrage de l’application.</span><span class="sxs-lookup"><span data-stu-id="19ea5-181">Razor view pre-compilation is enabled during publish by default, reducing the publish output size and application startup time.</span></span>

<span data-ttu-id="19ea5-182">Pour plus d’informations, consultez [Précompilation et compilation de vues Razor dans ASP.NET Core](xref:mvc/views/view-compilation).</span><span class="sxs-lookup"><span data-stu-id="19ea5-182">For more information, see [Razor view compilation and precompilation in ASP.NET Core](xref:mvc/views/view-compilation).</span></span>

## <a name="razor-support-for-c-71"></a><span data-ttu-id="19ea5-183">Prise en charge de Razor pour C# 7.1</span><span class="sxs-lookup"><span data-stu-id="19ea5-183">Razor support for C# 7.1</span></span>

<span data-ttu-id="19ea5-184">Le moteur de vue Razor a été mis à jour pour fonctionner avec le nouveau compilateur Roslyn.</span><span class="sxs-lookup"><span data-stu-id="19ea5-184">The Razor view engine has been updated to work with the new Roslyn compiler.</span></span> <span data-ttu-id="19ea5-185">Cela comprend la prise en charge des fonctionnalités de C# 7.1 telles que les expressions par défaut, la déduction des noms de tuples et les critères spéciaux avec les génériques.</span><span class="sxs-lookup"><span data-stu-id="19ea5-185">That includes support for C# 7.1 features like Default Expressions, Inferred Tuple Names, and Pattern-Matching with Generics.</span></span> <span data-ttu-id="19ea5-186">Pour utiliser C# 7.1 dans votre projet, ajoutez la propriété suivante dans votre fichier projet, puis rechargez la solution :</span><span class="sxs-lookup"><span data-stu-id="19ea5-186">To use C# 7.1 in your project, add the following property in your project file and then reload the solution:</span></span>

```xml
<LangVersion>latest</LangVersion>
```

<span data-ttu-id="19ea5-187">Pour plus d’informations sur l’état des fonctionnalités de C# 7.1, consultez le [dépôt GitHub de Roslyn](https://github.com/dotnet/roslyn/blob/master/docs/Language%20Feature%20Status.md).</span><span class="sxs-lookup"><span data-stu-id="19ea5-187">For information about the status of C# 7.1 features, see [the Roslyn GitHub repository](https://github.com/dotnet/roslyn/blob/master/docs/Language%20Feature%20Status.md).</span></span>

## <a name="other-documentation-updates-for-20"></a><span data-ttu-id="19ea5-188">Autres mises à jour de la documentation pour la version 2.0</span><span class="sxs-lookup"><span data-stu-id="19ea5-188">Other documentation updates for 2.0</span></span>

* [<span data-ttu-id="19ea5-189">Profils de publication Visual Studio pour le déploiement d’applications ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="19ea5-189">Visual Studio publish profiles for ASP.NET Core app deployment</span></span>](xref:host-and-deploy/visual-studio-publish-profiles)
* [<span data-ttu-id="19ea5-190">Gestion des clés</span><span class="sxs-lookup"><span data-stu-id="19ea5-190">Key Management</span></span>](xref:security/data-protection/implementation/key-management)
* [<span data-ttu-id="19ea5-191">Configurer l’authentification Facebook</span><span class="sxs-lookup"><span data-stu-id="19ea5-191">Configure Facebook authentication</span></span>](xref:security/authentication/facebook-logins)
* [<span data-ttu-id="19ea5-192">Configurer l’authentification Twitter</span><span class="sxs-lookup"><span data-stu-id="19ea5-192">Configure Twitter authentication</span></span>](xref:security/authentication/twitter-logins)
* [<span data-ttu-id="19ea5-193">Configurer l’authentification Google</span><span class="sxs-lookup"><span data-stu-id="19ea5-193">Configure Google authentication</span></span>](xref:security/authentication/google-logins)
* [<span data-ttu-id="19ea5-194">Configurer l’authentification de compte Microsoft</span><span class="sxs-lookup"><span data-stu-id="19ea5-194">Configure Microsoft Account authentication</span></span>](xref:security/authentication/microsoft-logins)

## <a name="migration-guidance"></a><span data-ttu-id="19ea5-195">Conseils de migration</span><span class="sxs-lookup"><span data-stu-id="19ea5-195">Migration guidance</span></span>

<span data-ttu-id="19ea5-196">Pour obtenir des conseils sur la migration d’applications ASP.NET Core 1.x vers ASP.NET Core 2.0, consultez les ressources suivantes :</span><span class="sxs-lookup"><span data-stu-id="19ea5-196">For guidance on how to migrate ASP.NET Core 1.x applications to ASP.NET Core 2.0, see the following resources:</span></span>

* [<span data-ttu-id="19ea5-197">Migrer d’ASP.NET Core 1.x vers ASP.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="19ea5-197">Migrate from ASP.NET Core 1.x to ASP.NET Core 2.0</span></span>](xref:migration/1x-to-2x/index)
* [<span data-ttu-id="19ea5-198">Migrer l’authentification et l’identité vers ASP.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="19ea5-198">Migrate Authentication and Identity to ASP.NET Core 2.0</span></span>](xref:migration/1x-to-2x/identity-2x)

## <a name="additional-information"></a><span data-ttu-id="19ea5-199">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="19ea5-199">Additional Information</span></span>

<span data-ttu-id="19ea5-200">Pour obtenir la liste complète des modifications, consultez les [Notes de publication d’ASP.NET Core 2.0 ](https://github.com/aspnet/Home/releases/tag/2.0.0).</span><span class="sxs-lookup"><span data-stu-id="19ea5-200">For the complete list of changes, see the [ASP.NET Core 2.0 Release Notes](https://github.com/aspnet/Home/releases/tag/2.0.0).</span></span>

<span data-ttu-id="19ea5-201">Pour être tenu au courant de la progression et des plans de l’équipe de développement ASP.NET Core, participez à la [réunion de la communauté ASP.NET](https://live.asp.net/).</span><span class="sxs-lookup"><span data-stu-id="19ea5-201">To connect with the ASP.NET Core development team's progress and plans, tune in to the [ASP.NET Community Standup](https://live.asp.net/).</span></span>