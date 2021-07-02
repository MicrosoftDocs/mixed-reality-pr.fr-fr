---
title: Recommandations en matière de codage
description: Principes et conventions de codage à suivre lors de la contribution à MRTK.
author: polar-kev
ms.author: kesemple
ms.date: 01/12/2021
keywords: unity, HoloLens, HoloLens 2, réalité mixte, développement, MRTK, C#,
ms.openlocfilehash: c14f5f72d391c5474a01c798bfdaa5529700a509
ms.sourcegitcommit: f338b1f121a10577bcce08a174e462cdc86d5874
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2021
ms.locfileid: "113175334"
---
# <a name="coding-guidelines"></a><span data-ttu-id="5c27d-104">Recommandations en matière de codage</span><span class="sxs-lookup"><span data-stu-id="5c27d-104">Coding guidelines</span></span>

<span data-ttu-id="5c27d-105">Ce document décrit les principes et conventions de codage à suivre pour contribuer à MRTK.</span><span class="sxs-lookup"><span data-stu-id="5c27d-105">This document outlines coding principles and conventions to follow when contributing to MRTK.</span></span>

---

## <a name="philosophy"></a><span data-ttu-id="5c27d-106">Principe</span><span class="sxs-lookup"><span data-stu-id="5c27d-106">Philosophy</span></span>

### <a name="be-concise-and-strive-for-simplicity"></a><span data-ttu-id="5c27d-107">Soyez concis et efforcez-vous de simplifier</span><span class="sxs-lookup"><span data-stu-id="5c27d-107">Be concise and strive for simplicity</span></span>

<span data-ttu-id="5c27d-108">La solution la plus simple est souvent la meilleure.</span><span class="sxs-lookup"><span data-stu-id="5c27d-108">The simplest solution is often the best.</span></span> <span data-ttu-id="5c27d-109">Il s’agit d’un objectif de remplacement de ces instructions et doit être l’objectif de toute activité de codage.</span><span class="sxs-lookup"><span data-stu-id="5c27d-109">This is an overriding aim of these guidelines and should be the goal of all coding activity.</span></span> <span data-ttu-id="5c27d-110">Une partie du simple est très concise et cohérente avec le code existant.</span><span class="sxs-lookup"><span data-stu-id="5c27d-110">Part of being simple is being concise, and consistent with existing code.</span></span> <span data-ttu-id="5c27d-111">Essayez de simplifier votre code.</span><span class="sxs-lookup"><span data-stu-id="5c27d-111">Try to keep your code simple.</span></span>

<span data-ttu-id="5c27d-112">Les lecteurs doivent uniquement rencontrer des artefacts qui fournissent des informations utiles.</span><span class="sxs-lookup"><span data-stu-id="5c27d-112">Readers should only encounter artifacts that provide useful information.</span></span> <span data-ttu-id="5c27d-113">Par exemple, les commentaires qui reexpliquent ce qui est évident ne fournissent pas d’informations supplémentaires et augmentent le bruit sur le rapport signal.</span><span class="sxs-lookup"><span data-stu-id="5c27d-113">For example, comments that restate what is obvious provide no extra information and increase the noise to signal ratio.</span></span>

<span data-ttu-id="5c27d-114">Simplifiez la logique du code.</span><span class="sxs-lookup"><span data-stu-id="5c27d-114">Keep code logic simple.</span></span> <span data-ttu-id="5c27d-115">Notez qu’il ne s’agit pas d’une instruction sur l’utilisation d’un nombre de lignes moins élevé, ce qui réduit la taille des noms d’identificateurs ou des accolades, mais aussi la réduction du nombre de concepts et l’optimisation de la visibilité de ceux-ci par le biais de modèles familiers.</span><span class="sxs-lookup"><span data-stu-id="5c27d-115">Note that this is not a statement about using the fewest number of lines, minimizing the size of identifier names or brace style, but about reducing the number of concepts and maximizing the visibility of those through familiar patterns.</span></span>

### <a name="produce-consistent-readable-code"></a><span data-ttu-id="5c27d-116">Produire du code cohérent et lisible</span><span class="sxs-lookup"><span data-stu-id="5c27d-116">Produce consistent, readable code</span></span>

<span data-ttu-id="5c27d-117">La lisibilité du code est corrélée avec un faible taux de défauts.</span><span class="sxs-lookup"><span data-stu-id="5c27d-117">Code readability is correlated with low defect rates.</span></span> <span data-ttu-id="5c27d-118">Efforcez-vous de créer du code facile à lire.</span><span class="sxs-lookup"><span data-stu-id="5c27d-118">Strive to create code that is easy to read.</span></span> <span data-ttu-id="5c27d-119">Efforcez-vous de créer du code avec une logique simple et de réutiliser les composants existants, car cela permet également de garantir l’exactitude.</span><span class="sxs-lookup"><span data-stu-id="5c27d-119">Strive to create code that has simple logic and re-uses existing components as it will also help ensure correctness.</span></span>

<span data-ttu-id="5c27d-120">Tous les détails du code que vous produisez, des détails les plus simples à l’exactitude du style et de la mise en forme cohérents.</span><span class="sxs-lookup"><span data-stu-id="5c27d-120">All details of the code you produce matter, from the most basic detail of correctness to consistent style and formatting.</span></span> <span data-ttu-id="5c27d-121">Assurez la cohérence de votre style de codage avec ce qui existe déjà, même s’il ne correspond pas à vos préférences.</span><span class="sxs-lookup"><span data-stu-id="5c27d-121">Keep your coding style consistent with what already exists, even if it is not matching your preference.</span></span> <span data-ttu-id="5c27d-122">Cela augmente la lisibilité de l’ensemble du code base.</span><span class="sxs-lookup"><span data-stu-id="5c27d-122">This increases the readability of the overall codebase.</span></span>

### <a name="support-configuring-components-both-in-editor-and-at-run-time"></a><span data-ttu-id="5c27d-123">Prendre en charge la configuration des composants à la fois dans l’éditeur et au moment de l’exécution</span><span class="sxs-lookup"><span data-stu-id="5c27d-123">Support configuring components both in editor and at run-time</span></span>

<span data-ttu-id="5c27d-124">MRTK prend en charge un ensemble diversifié d’utilisateurs : les personnes qui préfèrent configurer des composants dans l’éditeur Unity et charger des prefabs, ainsi que les personnes qui doivent instancier et configurer des objets au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="5c27d-124">MRTK supports a diverse set of users – people who prefer to configure components in the Unity editor and load prefabs, and people who need to instantiate and configure objects at run-time.</span></span>

<span data-ttu-id="5c27d-125">Tout votre code doit fonctionner à la fois par l’ajout d’un composant à un GameObject dans une scène enregistrée et par l’instanciation de ce composant dans le code.</span><span class="sxs-lookup"><span data-stu-id="5c27d-125">All your code should work by BOTH adding a component to a GameObject in a saved scene, and by instantiating that component in code.</span></span> <span data-ttu-id="5c27d-126">Les tests doivent inclure un cas de test pour l’instanciation de prefabs et l’instanciation, la configuration du composant au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="5c27d-126">Tests should include a test case both for instantiating prefabs and instantiating, configuring the component at runtime.</span></span>

### <a name="play-in-editor-is-your-first-and-primary-target-platform"></a><span data-ttu-id="5c27d-127">Play-in-Editor est votre première et plateforme cible principale</span><span class="sxs-lookup"><span data-stu-id="5c27d-127">Play-in-editor is your first and primary target platform</span></span>

<span data-ttu-id="5c27d-128">Play-in-Editor est le moyen le plus rapide d’effectuer une itération dans Unity.</span><span class="sxs-lookup"><span data-stu-id="5c27d-128">Play-In-Editor is the fastest way to iterate in Unity.</span></span> <span data-ttu-id="5c27d-129">Fournir aux clients des moyens d’effectuer des itérations rapidement leur permet de développer des solutions plus rapidement et de tester plus d’idées.</span><span class="sxs-lookup"><span data-stu-id="5c27d-129">Providing ways for our customers to iterate quickly allows them to both develop solutions more quickly and try out more ideas.</span></span> <span data-ttu-id="5c27d-130">En d’autres termes, l’optimisation de la vitesse de l’itération permet à nos clients d’obtenir davantage d’informations.</span><span class="sxs-lookup"><span data-stu-id="5c27d-130">In other words, maximizing the speed of iteration empowers our customers to achieve more.</span></span>

<span data-ttu-id="5c27d-131">Faites en sorte que tout fonctionne dans l’éditeur, puis faites-le fonctionner sur n’importe quelle autre plateforme.</span><span class="sxs-lookup"><span data-stu-id="5c27d-131">Make everything work in editor, then make it work on any other platform.</span></span> <span data-ttu-id="5c27d-132">Conservez-le dans l’éditeur.</span><span class="sxs-lookup"><span data-stu-id="5c27d-132">Keep it working in the editor.</span></span> <span data-ttu-id="5c27d-133">Il est facile d’ajouter une nouvelle plateforme à la lecture dans l’éditeur.</span><span class="sxs-lookup"><span data-stu-id="5c27d-133">It is easy to add a new platform to Play-In-Editor.</span></span> <span data-ttu-id="5c27d-134">Il est très difficile d’utiliser l’éditeur de lecture dans le cas où votre application fonctionne uniquement sur un appareil.</span><span class="sxs-lookup"><span data-stu-id="5c27d-134">It is very difficult to get Play-In-Editor working if your app only works on a device.</span></span>

### <a name="add-new-public-fields-properties-methods-and-serialized-private-fields-with-care"></a><span data-ttu-id="5c27d-135">Ajouter de nouveaux champs publics, propriétés, méthodes et champs privés sérialisés avec précaution</span><span class="sxs-lookup"><span data-stu-id="5c27d-135">Add new public fields, properties, methods and serialized private fields with care</span></span>

<span data-ttu-id="5c27d-136">Chaque fois que vous ajoutez une méthode publique, un champ, une propriété, elle devient partie intégrante de la surface de l’API publique de MRTK.</span><span class="sxs-lookup"><span data-stu-id="5c27d-136">Every time you add a public method, field, property, it becomes part of MRTK’s public API surface.</span></span> <span data-ttu-id="5c27d-137">Les champs privés marqués avec `[SerializeField]` exposent également des champs à l’éditeur et font partie de la surface de l’API publique.</span><span class="sxs-lookup"><span data-stu-id="5c27d-137">Private fields marked with `[SerializeField]` also expose fields to the editor and are part of the public API surface.</span></span> <span data-ttu-id="5c27d-138">D’autres personnes peuvent utiliser cette méthode publique, configurer des prefabs personnalisés avec votre champ public et prendre une dépendance sur celle-ci.</span><span class="sxs-lookup"><span data-stu-id="5c27d-138">Other people might use that public method, configure custom prefabs with your public field, and take a dependency on it.</span></span>

<span data-ttu-id="5c27d-139">Les nouveaux membres publics doivent être examinés avec soin.</span><span class="sxs-lookup"><span data-stu-id="5c27d-139">New public members should be carefully examined.</span></span> <span data-ttu-id="5c27d-140">Tout champ public devra être conservé à l’avenir.</span><span class="sxs-lookup"><span data-stu-id="5c27d-140">Any public field will need to be maintained in the future.</span></span> <span data-ttu-id="5c27d-141">N’oubliez pas que si le type d’un champ public (ou champ privé sérialisé) est modifié ou supprimé d’un monocomportement, cela risque de perturber d’autres personnes.</span><span class="sxs-lookup"><span data-stu-id="5c27d-141">Remember that if the type of a public field (or serialized private field) changes or gets removed from a MonoBehaviour, that could break other people.</span></span> <span data-ttu-id="5c27d-142">Le champ doit d’abord être déconseillé pour une version, et le code pour migrer les modifications pour les personnes ayant pris des dépendances doit être fourni.</span><span class="sxs-lookup"><span data-stu-id="5c27d-142">The field will need to first be deprecated for a release, and code to migrate changes for people that have taken dependencies would need to be provided.</span></span>

### <a name="prioritize-writing-tests"></a><span data-ttu-id="5c27d-143">Classer par ordre de priorité l’écriture des tests</span><span class="sxs-lookup"><span data-stu-id="5c27d-143">Prioritize writing tests</span></span>

<span data-ttu-id="5c27d-144">MRTK est un projet communautaire, modifié par un large éventail de contributeurs.</span><span class="sxs-lookup"><span data-stu-id="5c27d-144">MRTK is a community project, modified by a diverse range of contributors.</span></span> <span data-ttu-id="5c27d-145">Ces contributeurs peuvent ne pas connaître les détails de votre correction de bogue/fonctionnalité et rompre accidentellement votre fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="5c27d-145">These contributors may not know the details of your bug fix / feature, and accidentally break your feature.</span></span> <span data-ttu-id="5c27d-146">[MRTK exécute les tests d’intégration continue](https://dev.azure.com/aipmr/MixedRealityToolkit-Unity-CI/_build?definitionId=16) avant de terminer chaque requête de tirage.</span><span class="sxs-lookup"><span data-stu-id="5c27d-146">[MRTK runs continuous integration tests](https://dev.azure.com/aipmr/MixedRealityToolkit-Unity-CI/_build?definitionId=16) before completing every pull request.</span></span> <span data-ttu-id="5c27d-147">Les modifications qui interrompent les tests ne peuvent pas être archivées.</span><span class="sxs-lookup"><span data-stu-id="5c27d-147">Changes that break tests cannot be checked in.</span></span> <span data-ttu-id="5c27d-148">Par conséquent, les tests constituent la meilleure façon de s’assurer que les autres personnes ne perturbent pas votre fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="5c27d-148">Therefore, tests are the best way to ensure that other people do not break your feature.</span></span>

<span data-ttu-id="5c27d-149">Quand vous résolvez un bogue, écrivez un test pour vous assurer qu’il n’est pas régressé à l’avenir.</span><span class="sxs-lookup"><span data-stu-id="5c27d-149">When you fix a bug, write a test to ensure it does not regress in the future.</span></span> <span data-ttu-id="5c27d-150">Si vous ajoutez une fonctionnalité, écrivez des tests qui vérifient que votre fonctionnalité fonctionne.</span><span class="sxs-lookup"><span data-stu-id="5c27d-150">If adding a feature, write tests that verify your feature works.</span></span> <span data-ttu-id="5c27d-151">Cela est requis pour toutes les fonctionnalités d’expérience utilisateur, à l’exception des fonctionnalités expérimentales.</span><span class="sxs-lookup"><span data-stu-id="5c27d-151">This is required for all UX features except experimental features.</span></span>

## <a name="c-coding-conventions"></a><span data-ttu-id="5c27d-152">Conventions de codage C#</span><span class="sxs-lookup"><span data-stu-id="5c27d-152">C# Coding conventions</span></span>

### <a name="script-license-information-headers"></a><span data-ttu-id="5c27d-153">En-têtes d’informations de licence de script</span><span class="sxs-lookup"><span data-stu-id="5c27d-153">Script license information headers</span></span>

<span data-ttu-id="5c27d-154">Tous les employés de Microsoft qui apportent de nouveaux fichiers doivent ajouter l’en-tête de licence standard suivant en haut de tous les nouveaux fichiers, exactement comme indiqué ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="5c27d-154">All Microsoft employees contributing new files should add the following standard License header at the top of any new files, exactly as shown below:</span></span>

```c#
// Copyright (c) Microsoft Corporation.
// Licensed under the MIT License.
```

### <a name="function--method-summary-headers"></a><span data-ttu-id="5c27d-155">En-têtes de résumé de fonction/méthode</span><span class="sxs-lookup"><span data-stu-id="5c27d-155">Function / method summary headers</span></span>

<span data-ttu-id="5c27d-156">Toutes les classes publiques, les structs, les enums, les fonctions, les propriétés, les champs publiés dans MRTK doivent être décrits comme à son usage et à leur utilisation, exactement comme indiqué ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="5c27d-156">All public classes, structs, enums, functions, properties, fields posted to the MRTK should be described as to its purpose and use, exactly as shown below:</span></span>

```c#
/// <summary>
/// The Controller definition defines the Controller as defined by the SDK / Unity.
/// </summary>
public struct Controller
{
    /// <summary>
    /// The ID assigned to the Controller
    /// </summary>
    public string ID;
}
```

<span data-ttu-id="5c27d-157">Cela garantit que la documentation est correctement générée et diffusée pour toutes les classes, méthodes et propriétés.</span><span class="sxs-lookup"><span data-stu-id="5c27d-157">This ensures documentation is properly generated and disseminated for all all classes, methods, and properties.</span></span>

<span data-ttu-id="5c27d-158">Tous les fichiers de script soumis sans balises de résumé appropriées seront rejetés.</span><span class="sxs-lookup"><span data-stu-id="5c27d-158">Any script files submitted without proper summary tags will be rejected.</span></span>

### <a name="mrtk-namespace-rules"></a><span data-ttu-id="5c27d-159">Règles d’espace de noms MRTK</span><span class="sxs-lookup"><span data-stu-id="5c27d-159">MRTK namespace rules</span></span>

<span data-ttu-id="5c27d-160">la réalité mixte Shared Computer Toolkit utilise un modèle d’espace de noms basé sur des fonctionnalités, où tous les espaces de noms fondamentaux commencent par «Microsoft. MixedReality. Shared Computer Toolkit».</span><span class="sxs-lookup"><span data-stu-id="5c27d-160">The Mixed Reality Toolkit uses a feature based namespace model, where all foundational namespaces begin with "Microsoft.MixedReality.Toolkit".</span></span> <span data-ttu-id="5c27d-161">En général, vous n’avez pas besoin de spécifier la couche du kit de tâches (par exemple, Core, Providers, services) dans vos espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="5c27d-161">In general, you need not specify the toolkit layer (ex: Core, Providers, Services) in your namespaces.</span></span>

<span data-ttu-id="5c27d-162">Les espaces de noms actuellement définis sont :</span><span class="sxs-lookup"><span data-stu-id="5c27d-162">The currently defined namespaces are:</span></span>

- <span data-ttu-id="5c27d-163">Microsoft. MixedReality. Shared Computer Toolkit</span><span class="sxs-lookup"><span data-stu-id="5c27d-163">Microsoft.MixedReality.Toolkit</span></span>
- <span data-ttu-id="5c27d-164">Microsoft. MixedReality. Shared Computer Toolkit. Bordure</span><span class="sxs-lookup"><span data-stu-id="5c27d-164">Microsoft.MixedReality.Toolkit.Boundary</span></span>
- <span data-ttu-id="5c27d-165">Microsoft. MixedReality. Shared Computer Toolkit. Diagnostics</span><span class="sxs-lookup"><span data-stu-id="5c27d-165">Microsoft.MixedReality.Toolkit.Diagnostics</span></span>
- <span data-ttu-id="5c27d-166">Microsoft. MixedReality. Shared Computer Toolkit. Éditeurs</span><span class="sxs-lookup"><span data-stu-id="5c27d-166">Microsoft.MixedReality.Toolkit.Editor</span></span>
- <span data-ttu-id="5c27d-167">Microsoft. MixedReality. Shared Computer Toolkit. Entrée</span><span class="sxs-lookup"><span data-stu-id="5c27d-167">Microsoft.MixedReality.Toolkit.Input</span></span>
- <span data-ttu-id="5c27d-168">Microsoft. MixedReality. Shared Computer Toolkit. SpatialAwareness</span><span class="sxs-lookup"><span data-stu-id="5c27d-168">Microsoft.MixedReality.Toolkit.SpatialAwareness</span></span>
- <span data-ttu-id="5c27d-169">Microsoft. MixedReality. Shared Computer Toolkit. Porte</span><span class="sxs-lookup"><span data-stu-id="5c27d-169">Microsoft.MixedReality.Toolkit.Teleport</span></span>
- <span data-ttu-id="5c27d-170">Microsoft. MixedReality. Shared Computer Toolkit. Utilitaires</span><span class="sxs-lookup"><span data-stu-id="5c27d-170">Microsoft.MixedReality.Toolkit.Utilities</span></span>

<span data-ttu-id="5c27d-171">Pour les espaces de noms avec une grande quantité de types, il est acceptable de créer un nombre limité de sous-espaces de noms pour faciliter l’utilisation de l’étendue.</span><span class="sxs-lookup"><span data-stu-id="5c27d-171">For namespaces with a large amount of types, it is acceptable to create a limited number of sub-namespaces to aid in scoping usage.</span></span>

<span data-ttu-id="5c27d-172">L’omission de l’espace de noms pour une interface, une classe ou un type de données entraîne le blocage de votre modification.</span><span class="sxs-lookup"><span data-stu-id="5c27d-172">Omitting the namespace for an interface, class or data type will cause your change to be blocked.</span></span>

### <a name="adding-new-monobehaviour-scripts"></a><span data-ttu-id="5c27d-173">Ajout de nouveaux scripts monocomportement</span><span class="sxs-lookup"><span data-stu-id="5c27d-173">Adding new MonoBehaviour scripts</span></span>

<span data-ttu-id="5c27d-174">Lorsque vous ajoutez de nouveaux scripts monocomportement avec une requête de tirage, assurez-vous que l' [`AddComponentMenu`](https://docs.unity3d.com/ScriptReference/AddComponentMenu.html) attribut est appliqué à tous les fichiers applicables.</span><span class="sxs-lookup"><span data-stu-id="5c27d-174">When adding new MonoBehaviour scripts with a pull request, ensure the [`AddComponentMenu`](https://docs.unity3d.com/ScriptReference/AddComponentMenu.html) attribute is applied to all applicable files.</span></span> <span data-ttu-id="5c27d-175">Cela permet de s’assurer que le composant est facilement détectable dans l’éditeur, sous le bouton *Ajouter un composant* .</span><span class="sxs-lookup"><span data-stu-id="5c27d-175">This ensures the component is easily discoverable in the editor under the *Add Component* button.</span></span> <span data-ttu-id="5c27d-176">L’indicateur d’attribut n’est pas nécessaire si le composant ne peut pas s’afficher dans un éditeur tel qu’une classe abstraite.</span><span class="sxs-lookup"><span data-stu-id="5c27d-176">The attribute flag is not necessary if the component cannot show up in editor such as an abstract class.</span></span>

<span data-ttu-id="5c27d-177">Dans l’exemple ci-dessous, le *package* doit être rempli avec l’emplacement du package du composant.</span><span class="sxs-lookup"><span data-stu-id="5c27d-177">In the example below, the *Package here* should be filled with the package location of the component.</span></span> <span data-ttu-id="5c27d-178">Si vous placez un élément dans le dossier *MRTK/SDK* , le package sera le *Kit de développement logiciel (SDK)*.</span><span class="sxs-lookup"><span data-stu-id="5c27d-178">If placing an item in *MRTK/SDK* folder, then the package will be *SDK*.</span></span>

```c#
[AddComponentMenu("Scripts/MRTK/{Package here}/MyNewComponent")]
public class MyNewComponent : MonoBehaviour
```

### <a name="adding-new-unity-inspector-scripts"></a><span data-ttu-id="5c27d-179">Ajout de nouveaux scripts d’inspecteur Unity</span><span class="sxs-lookup"><span data-stu-id="5c27d-179">Adding new Unity inspector scripts</span></span>

<span data-ttu-id="5c27d-180">En général, essayez d’éviter de créer des scripts d’inspecteur personnalisés pour les composants MRTK.</span><span class="sxs-lookup"><span data-stu-id="5c27d-180">In general, try to avoid creating custom inspector scripts for MRTK components.</span></span> <span data-ttu-id="5c27d-181">Il ajoute une surcharge et une gestion supplémentaires du code base qui peuvent être gérées par le moteur Unity.</span><span class="sxs-lookup"><span data-stu-id="5c27d-181">It adds additional overhead and management of the codebase that could be handled by the Unity engine.</span></span>

<span data-ttu-id="5c27d-182">Si une classe Inspector est nécessaire, essayez d’utiliser Unity [`DrawDefaultInspector()`](https://docs.unity3d.com/ScriptReference/Editor.DrawDefaultInspector.html) .</span><span class="sxs-lookup"><span data-stu-id="5c27d-182">If an inspector class is necessary, try to use Unity's [`DrawDefaultInspector()`](https://docs.unity3d.com/ScriptReference/Editor.DrawDefaultInspector.html).</span></span> <span data-ttu-id="5c27d-183">Cela simplifie la classe Inspector et laisse une grande partie du travail à Unity.</span><span class="sxs-lookup"><span data-stu-id="5c27d-183">This again simplifies the inspector class and leaves much of the work to Unity.</span></span>

```c#
public override void OnInspectorGUI()
{
    // Do some custom calculations or checks
    // ....
    DrawDefaultInspector();
}
```

<span data-ttu-id="5c27d-184">Si le rendu personnalisé est requis dans la classe Inspector, essayez d’utiliser [`SerializedProperty`](https://docs.unity3d.com/ScriptReference/SerializedProperty.html) et [`EditorGUILayout.PropertyField`](https://docs.unity3d.com/ScriptReference/EditorGUILayout.PropertyField.html) .</span><span class="sxs-lookup"><span data-stu-id="5c27d-184">If custom rendering is required in the inspector class, try to utilize [`SerializedProperty`](https://docs.unity3d.com/ScriptReference/SerializedProperty.html) and [`EditorGUILayout.PropertyField`](https://docs.unity3d.com/ScriptReference/EditorGUILayout.PropertyField.html).</span></span> <span data-ttu-id="5c27d-185">Ainsi, Unity gère correctement le rendu des prefabs imbriqués et des valeurs modifiées.</span><span class="sxs-lookup"><span data-stu-id="5c27d-185">This will ensure Unity correctly handles rendering nested prefabs and modified values.</span></span>

<span data-ttu-id="5c27d-186">Si [`EditorGUILayout.PropertyField`](https://docs.unity3d.com/ScriptReference/EditorGUILayout.PropertyField.html) ne peut pas être utilisé en raison d’une spécification dans une logique personnalisée, assurez-vous que toute utilisation est encapsulée autour d’un [`EditorGUI.PropertyScope`](https://docs.unity3d.com/ScriptReference/EditorGUI.PropertyScope.html) .</span><span class="sxs-lookup"><span data-stu-id="5c27d-186">If [`EditorGUILayout.PropertyField`](https://docs.unity3d.com/ScriptReference/EditorGUILayout.PropertyField.html) cannot be used due to a requirement in custom logic, ensure all usage is wrapped around a [`EditorGUI.PropertyScope`](https://docs.unity3d.com/ScriptReference/EditorGUI.PropertyScope.html).</span></span> <span data-ttu-id="5c27d-187">Cela permet de garantir que Unity rend correctement l’inspecteur pour les prefabs imbriquées et les valeurs modifiées avec la propriété donnée.</span><span class="sxs-lookup"><span data-stu-id="5c27d-187">This will ensure Unity renders the inspector correctly for nested prefabs and modified values with the given property.</span></span>

<span data-ttu-id="5c27d-188">En outre, essayez de décorer la classe Inspector personnalisée avec un [`CanEditMultipleObjects`](https://docs.unity3d.com/ScriptReference/CanEditMultipleObjects.html) .</span><span class="sxs-lookup"><span data-stu-id="5c27d-188">Furthermore, try to decorate the custom inspector class with a [`CanEditMultipleObjects`](https://docs.unity3d.com/ScriptReference/CanEditMultipleObjects.html).</span></span> <span data-ttu-id="5c27d-189">Cette balise permet de s’assurer que plusieurs objets avec ce composant dans la scène peuvent être sélectionnés et modifiés ensemble.</span><span class="sxs-lookup"><span data-stu-id="5c27d-189">This tag ensure multiple objects with this component in the scene can be selected and modified together.</span></span> <span data-ttu-id="5c27d-190">Toutes les nouvelles classes Inspector doivent vérifier que leur code fonctionne dans cette situation dans la scène.</span><span class="sxs-lookup"><span data-stu-id="5c27d-190">Any new inspector classes should test that their code works in this situation in the scene.</span></span>

```c#
    // Example inspector class demonstrating usage of SerializedProperty & EditorGUILayout.PropertyField
    // as well as use of EditorGUI.PropertyScope for custom property logic
    [CustomEditor(typeof(MyComponent))]
    public class MyComponentInspector : UnityEditor.Editor
    {
        private SerializedProperty myProperty;
        private SerializedProperty handedness;

        protected virtual void OnEnable()
        {
            myProperty = serializedObject.FindProperty("myProperty");
            handedness = serializedObject.FindProperty("handedness");
        }

        public override void OnInspectorGUI()
        {
            EditorGUILayout.PropertyField(destroyOnSourceLost);

            Rect position = EditorGUILayout.GetControlRect();
            var label = new GUIContent(handedness.displayName);
            using (new EditorGUI.PropertyScope(position, label, handedness))
            {
                var currentHandedness = (Handedness)handedness.enumValueIndex;

                handedness.enumValueIndex = (int)(Handedness)EditorGUI.EnumPopup(
                    position,
                    label,
                    currentHandedness,
                    (value) => {
                        // This function is executed by Unity to determine if a possible enum value
                        // is valid for selection in the editor view
                        // In this case, only Handedness.Left and Handedness.Right can be selected
                        return (Handedness)value == Handedness.Left
                        || (Handedness)value == Handedness.Right;
                    });
            }
        }
    }
```

### <a name="adding-new-scriptableobjects"></a><span data-ttu-id="5c27d-191">Ajout de New ScriptableObjects</span><span class="sxs-lookup"><span data-stu-id="5c27d-191">Adding new ScriptableObjects</span></span>

<span data-ttu-id="5c27d-192">Lorsque vous ajoutez de nouveaux scripts ScriptableObject, vérifiez que l' [`CreateAssetMenu`](https://docs.unity3d.com/ScriptReference/CreateAssetMenu.html) attribut est appliqué à tous les fichiers applicables.</span><span class="sxs-lookup"><span data-stu-id="5c27d-192">When adding new ScriptableObject scripts, ensure the [`CreateAssetMenu`](https://docs.unity3d.com/ScriptReference/CreateAssetMenu.html) attribute is applied to all applicable files.</span></span> <span data-ttu-id="5c27d-193">Cela permet de s’assurer que le composant est facilement détectable dans l’éditeur par le biais des menus de création de composants.</span><span class="sxs-lookup"><span data-stu-id="5c27d-193">This ensures the component is easily discoverable in the editor via the asset creation menus.</span></span> <span data-ttu-id="5c27d-194">L’indicateur d’attribut n’est pas nécessaire si le composant ne peut pas s’afficher dans un éditeur tel qu’une classe abstraite.</span><span class="sxs-lookup"><span data-stu-id="5c27d-194">The attribute flag is not necessary if the component cannot show up in editor such as an abstract class.</span></span>

<span data-ttu-id="5c27d-195">Dans l’exemple ci-dessous, le *sous-dossier* doit être rempli avec le sous-dossier MRTK, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="5c27d-195">In the example below, the *Subfolder* should be filled with the MRTK subfolder, if applicable.</span></span> <span data-ttu-id="5c27d-196">Si vous placez un élément dans le dossier *MRTK/Providers* , le package sera *fournisseurs*.</span><span class="sxs-lookup"><span data-stu-id="5c27d-196">If placing an item in *MRTK/Providers* folder, then the package will be *Providers*.</span></span> <span data-ttu-id="5c27d-197">Si vous placez un élément dans le dossier *MRTK/Core* , affectez-lui la valeur « profiles ».</span><span class="sxs-lookup"><span data-stu-id="5c27d-197">If placing an item in the *MRTK/Core* folder, set this to "Profiles".</span></span>

<span data-ttu-id="5c27d-198">Dans l’exemple ci-dessous, *MyNewService | MyNewProvider* doit être rempli avec le nom de votre nouvelle classe, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="5c27d-198">In the example below, the *MyNewService | MyNewProvider* should be filled with the your new class' name, if applicable.</span></span> <span data-ttu-id="5c27d-199">Si vous placez un élément dans le dossier *MixedRealityToolkit* , laissez cette chaîne vide.</span><span class="sxs-lookup"><span data-stu-id="5c27d-199">If placing an item in the *MixedRealityToolkit* folder, leave this string out.</span></span>

```c#
[CreateAssetMenu(fileName = "MyNewProfile", menuName = "Mixed Reality Toolkit/{Subfolder}/{MyNewService | MyNewProvider}/MyNewProfile")]
public class MyNewProfile : ScriptableObject
```

### <a name="logging"></a><span data-ttu-id="5c27d-200">Journalisation</span><span class="sxs-lookup"><span data-stu-id="5c27d-200">Logging</span></span>

<span data-ttu-id="5c27d-201">Lorsque vous ajoutez de nouvelles fonctionnalités ou mettez à jour des fonctionnalités existantes, envisagez d’ajouter des journaux DebugUtilities. LogVerbose à du code intéressant qui peut s’avérer utile pour un débogage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="5c27d-201">When adding new features or updating existing features, consider adding DebugUtilities.LogVerbose logs to interesting code that may be useful for future debugging.</span></span> <span data-ttu-id="5c27d-202">Il y a un compromis entre l’ajout de la journalisation et le bruit ajouté et la journalisation insuffisante (ce qui rend le diagnostic difficile).</span><span class="sxs-lookup"><span data-stu-id="5c27d-202">There's a tradeoff here between adding logging and the added noise and not enough logging (which makes diagnosis difficult).</span></span>

<span data-ttu-id="5c27d-203">Un exemple intéressant où la journalisation est utile (avec une charge utile intéressante) :</span><span class="sxs-lookup"><span data-stu-id="5c27d-203">An interesting example where having logging is useful (along with interesting payload):</span></span>

```c#
DebugUtilities.LogVerboseFormat("RaiseSourceDetected: Source ID: {0}, Source Type: {1}", source.SourceId, source.SourceType);
```

<span data-ttu-id="5c27d-204">Ce type de journalisation peut vous aider à détecter des problèmes tels que des erreurs [https://github.com/microsoft/MixedRealityToolkit-Unity/issues/8016](https://github.com/microsoft/MixedRealityToolkit-Unity/issues/8016) de source incompatible détectées et des événements de perte de source.</span><span class="sxs-lookup"><span data-stu-id="5c27d-204">This type of logging can help catch issues like [https://github.com/microsoft/MixedRealityToolkit-Unity/issues/8016](https://github.com/microsoft/MixedRealityToolkit-Unity/issues/8016), which were caused by mismatched source detected and source lost events.</span></span>

<span data-ttu-id="5c27d-205">Évitez d’ajouter des journaux pour les données et les événements qui se produisent dans tous les cas où la journalisation idéale devrait couvrir des événements « intéressants » pilotés par des entrées d’utilisateur distinctes (c’est-à-dire un « clic » par un utilisateur et l’ensemble de modifications et d’événements provenant de qui sont intéressants pour le journal).</span><span class="sxs-lookup"><span data-stu-id="5c27d-205">Avoid adding logs for data and events that are occurring on every frame - ideally logging should cover "interesting" events driven by distinct user inputs (i.e. a "click" by a user and the set of changes and events that come from that are interesting to log).</span></span> <span data-ttu-id="5c27d-206">L’État en cours « l’utilisateur maintient toujours un geste » enregistré dans chaque cadre n’est pas intéressant et surcharge les journaux.</span><span class="sxs-lookup"><span data-stu-id="5c27d-206">The ongoing state of "user is still holding a gesture" logged every frame is not interesting and will overwhelm the logs.</span></span>

<span data-ttu-id="5c27d-207">Notez que cette journalisation documentée n’est pas activée par défaut (elle doit être activée dans les [paramètres du système de diagnostic](../features/diagnostics/configuring-diagnostics.md#enable-verbose-logging)).</span><span class="sxs-lookup"><span data-stu-id="5c27d-207">Note that this verbose logging is not turned on by default (it must be enabled in the [Diagnostic System settings](../features/diagnostics/configuring-diagnostics.md#enable-verbose-logging))</span></span>

### <a name="spaces-vs-tabs"></a><span data-ttu-id="5c27d-208">Espaces et tabulations</span><span class="sxs-lookup"><span data-stu-id="5c27d-208">Spaces vs tabs</span></span>

<span data-ttu-id="5c27d-209">Veillez à utiliser 4 espaces à la place des onglets lors de la contribution à ce projet.</span><span class="sxs-lookup"><span data-stu-id="5c27d-209">Please be sure to use 4 spaces instead of tabs when contributing to this project.</span></span>

### <a name="spacing"></a><span data-ttu-id="5c27d-210">Espacement</span><span class="sxs-lookup"><span data-stu-id="5c27d-210">Spacing</span></span>

<span data-ttu-id="5c27d-211">N’ajoutez pas d’espaces supplémentaires entre les crochets et les parenthèses :</span><span class="sxs-lookup"><span data-stu-id="5c27d-211">Do not to add additional spaces between square brackets and parenthesis:</span></span>

#### <a name="dont"></a><span data-ttu-id="5c27d-212">À ne pas faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-212">Don't</span></span>

```c#
private Foo()
{
    int[ ] var = new int [ 9 ];
    Vector2 vector = new Vector2 ( 0f, 10f );
}

```

#### <a name="do"></a><span data-ttu-id="5c27d-213">À faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-213">Do</span></span>

```c#
private Foo()
{
    int[] var = new int[9];
    Vector2 vector = new Vector2(0f, 10f);
}
```

### <a name="naming-conventions"></a><span data-ttu-id="5c27d-214">Conventions d’affectation de noms</span><span class="sxs-lookup"><span data-stu-id="5c27d-214">Naming conventions</span></span>

<span data-ttu-id="5c27d-215">Utilisez toujours `PascalCase` pour les propriétés.</span><span class="sxs-lookup"><span data-stu-id="5c27d-215">Always use `PascalCase` for properties.</span></span> <span data-ttu-id="5c27d-216">Utilisez `camelCase` pour la plupart des champs, à l’exception `PascalCase` des `static readonly` `const` champs et.</span><span class="sxs-lookup"><span data-stu-id="5c27d-216">Use `camelCase` for most fields, except use `PascalCase` for `static readonly` and `const` fields.</span></span> <span data-ttu-id="5c27d-217">La seule exception concerne les structures de données qui requièrent que les champs soient sérialisés par le `JsonUtility` .</span><span class="sxs-lookup"><span data-stu-id="5c27d-217">The only exception to this is for data structures that require the fields to be serialized by the `JsonUtility`.</span></span>

#### <a name="dont"></a><span data-ttu-id="5c27d-218">À ne pas faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-218">Don't</span></span>

```c#
public string myProperty; // <- Starts with a lowercase letter
private string MyField; // <- Starts with an uppercase letter
```

#### <a name="do"></a><span data-ttu-id="5c27d-219">À faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-219">Do</span></span>

```c#
public string MyProperty;
protected string MyProperty;
private static readonly string MyField;
private string myField;
```

### <a name="access-modifiers"></a><span data-ttu-id="5c27d-220">Modificateurs d’accès</span><span class="sxs-lookup"><span data-stu-id="5c27d-220">Access modifiers</span></span>

<span data-ttu-id="5c27d-221">Déclarez toujours un modificateur d’accès pour tous les champs, propriétés et méthodes.</span><span class="sxs-lookup"><span data-stu-id="5c27d-221">Always declare an access modifier for all fields, properties and methods.</span></span>

- <span data-ttu-id="5c27d-222">Toutes les méthodes de l’API Unity doivent être `private` par défaut, sauf si vous devez les substituer dans une classe dérivée.</span><span class="sxs-lookup"><span data-stu-id="5c27d-222">All Unity API Methods should be `private` by default, unless you need to override them in a derived class.</span></span> <span data-ttu-id="5c27d-223">Dans ce cas, `protected` doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="5c27d-223">In this case `protected` should be used.</span></span>

- <span data-ttu-id="5c27d-224">Les champs doivent toujours être `private` , avec des `public` `protected` accesseurs de propriété ou.</span><span class="sxs-lookup"><span data-stu-id="5c27d-224">Fields should always be `private`, with `public` or `protected` property accessors.</span></span>

- <span data-ttu-id="5c27d-225">Utiliser des [membres expression-astiers](https://github.com/dotnet/roslyn/wiki/New-Language-Features-in-C%23-6#expression-bodied-function-members) et des [propriétés auto](https://github.com/dotnet/roslyn/wiki/New-Language-Features-in-C%23-6#auto-property-enhancements) lorsque cela est possible</span><span class="sxs-lookup"><span data-stu-id="5c27d-225">Use [expression-bodied members](https://github.com/dotnet/roslyn/wiki/New-Language-Features-in-C%23-6#expression-bodied-function-members) and [auto properties](https://github.com/dotnet/roslyn/wiki/New-Language-Features-in-C%23-6#auto-property-enhancements) where possible</span></span>

#### <a name="dont"></a><span data-ttu-id="5c27d-226">À ne pas faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-226">Don't</span></span>

```c#
// protected field should be private
protected int myVariable = 0;

// property should have protected setter
public int MyVariable => myVariable;

// No public / private access modifiers
void Foo() { }
void Bar() { }
```

#### <a name="do"></a><span data-ttu-id="5c27d-227">À faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-227">Do</span></span>

```c#
public int MyVariable { get; protected set; } = 0;

private void Foo() { }
public void Bar() { }
protected virtual void FooBar() { }
```

### <a name="use-braces"></a><span data-ttu-id="5c27d-228">Utiliser des accolades</span><span class="sxs-lookup"><span data-stu-id="5c27d-228">Use braces</span></span>

<span data-ttu-id="5c27d-229">Utilisez toujours les accolades après chaque bloc d’instructions et placez-les sur la ligne suivante.</span><span class="sxs-lookup"><span data-stu-id="5c27d-229">Always use braces after each statement block, and place them on the next line.</span></span>

#### <a name="dont"></a><span data-ttu-id="5c27d-230">Pratiques déconseillées</span><span class="sxs-lookup"><span data-stu-id="5c27d-230">Don't</span></span>

```c#
private Foo()
{
    if (Bar==null) // <- missing braces surrounding if action
        DoThing();
    else
        DoTheOtherThing();
}
```

#### <a name="dont"></a><span data-ttu-id="5c27d-231">À ne pas faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-231">Don't</span></span>

```c#
private Foo() { // <- Open bracket on same line
    if (Bar==null) DoThing(); <- if action on same line with no surrounding brackets
    else DoTheOtherThing();
}
```

#### <a name="do"></a><span data-ttu-id="5c27d-232">À faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-232">Do</span></span>

```c#
private Foo()
{
    if (Bar==true)
    {
        DoThing();
    }
    else
    {
        DoTheOtherThing();
    }
}
```

### <a name="public-classes-structs-and-enums-should-all-go-in-their-own-files"></a><span data-ttu-id="5c27d-233">Les classes, structs et enums publics doivent tous se trouver dans leurs propres fichiers</span><span class="sxs-lookup"><span data-stu-id="5c27d-233">Public classes, structs, and enums should all go in their own files</span></span>

<span data-ttu-id="5c27d-234">Si la classe, le struct ou l’enum peut être rendu privé, il est possible de l’inclure dans le même fichier.</span><span class="sxs-lookup"><span data-stu-id="5c27d-234">If the class, struct, or enum can be made private then it's okay to be included in the same file.</span></span>  <span data-ttu-id="5c27d-235">Cela évite les problèmes de compilation avec Unity et s’assure que l’abstraction du code appropriée se produit, elle réduit également les conflits et les modifications avec rupture lorsque le code doit changer.</span><span class="sxs-lookup"><span data-stu-id="5c27d-235">This avoids compilations issues with Unity and ensure that proper code abstraction occurs, it also reduces conflicts and breaking changes when code needs to change.</span></span>

#### <a name="dont"></a><span data-ttu-id="5c27d-236">À ne pas faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-236">Don't</span></span>

```c#
public class MyClass
{
    public struct MyStruct() { }
    public enum MyEnumType() { }
    public class MyNestedClass() { }
}
```

#### <a name="do"></a><span data-ttu-id="5c27d-237">À faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-237">Do</span></span>

```c#
 // Private references for use inside the class only
public class MyClass
{
    private struct MyStruct() { }
    private enum MyEnumType() { }
    private class MyNestedClass() { }
}
```

#### <a name="do"></a><span data-ttu-id="5c27d-238">Pratiques conseillées</span><span class="sxs-lookup"><span data-stu-id="5c27d-238">Do</span></span>

<span data-ttu-id="5c27d-239">MyStruct. cs</span><span class="sxs-lookup"><span data-stu-id="5c27d-239">MyStruct.cs</span></span>

```c#
// Public Struct / Enum definitions for use in your class.  Try to make them generic for reuse.
public struct MyStruct
{
    public string Var1;
    public string Var2;
}
```

<span data-ttu-id="5c27d-240">MyEnumType. cs</span><span class="sxs-lookup"><span data-stu-id="5c27d-240">MyEnumType.cs</span></span>

```c#
public enum MuEnumType
{
    Value1,
    Value2 // <- note, no "," on last value to denote end of list.
}
```

<span data-ttu-id="5c27d-241">MyClass. cs</span><span class="sxs-lookup"><span data-stu-id="5c27d-241">MyClass.cs</span></span>

```c#
public class MyClass
{
    private MyStruct myStructReference;
    private MyEnumType myEnumReference;
}
```

### <a name="initialize-enums"></a><span data-ttu-id="5c27d-242">Initialiser les énumérations</span><span class="sxs-lookup"><span data-stu-id="5c27d-242">Initialize enums</span></span>

<span data-ttu-id="5c27d-243">Pour vous assurer que tous les enums sont correctement initialisés à partir de 0, .NET vous donne un raccourci tidy pour initialiser automatiquement l’énumération en ajoutant simplement la première valeur (Starter).</span><span class="sxs-lookup"><span data-stu-id="5c27d-243">To ensure all enums are initialized correctly starting at 0, .NET gives you a tidy shortcut to automatically initialize the enum by just adding the first (starter) value.</span></span> <span data-ttu-id="5c27d-244">(par exemple, valeur 1 = 0 les valeurs restantes ne sont pas requises)</span><span class="sxs-lookup"><span data-stu-id="5c27d-244">(e.g Value 1 = 0 Remaining values are not required)</span></span>

#### <a name="dont"></a><span data-ttu-id="5c27d-245">À ne pas faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-245">Don't</span></span>

```c#
public enum Value
{
    Value1, <- no initializer
    Value2,
    Value3
}
```

#### <a name="do"></a><span data-ttu-id="5c27d-246">À faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-246">Do</span></span>

```c#
public enum ValueType
{
    Value1 = 0,
    Value2,
    Value3
}
```

### <a name="order-enums-for-appropriate-extension"></a><span data-ttu-id="5c27d-247">Commandes enums pour l’extension appropriée</span><span class="sxs-lookup"><span data-stu-id="5c27d-247">Order enums for appropriate extension</span></span>

<span data-ttu-id="5c27d-248">Si une énumération est susceptible d’être étendue à l’avenir, il est essentiel de classer les valeurs par défaut en haut de l’énumération, ce qui garantit que les index enum ne sont pas affectés par de nouveaux ajouts.</span><span class="sxs-lookup"><span data-stu-id="5c27d-248">It is critical that if an Enum is likely to be extended in the future, to order defaults at the top of the Enum, this ensures Enum indexes are not affected with new additions.</span></span>

#### <a name="dont"></a><span data-ttu-id="5c27d-249">À ne pas faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-249">Don't</span></span>

```c#
public enum SDKType
{
    WindowsMR,
    OpenVR,
    OpenXR,
    None, <- default value not at start
    Other <- anonymous value left to end of enum
}
```

#### <a name="do"></a><span data-ttu-id="5c27d-250">À faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-250">Do</span></span>

```c#
/// <summary>
/// The SDKType lists the VR SDKs that are supported by the MRTK
/// Initially, this lists proposed SDKs, not all may be implemented at this time (please see ReleaseNotes for more details)
/// </summary>
public enum SDKType
{
    /// <summary>
    /// No specified type or Standalone / non-VR type
    /// </summary>
    None = 0,
    /// <summary>
    /// Undefined SDK.
    /// </summary>
    Other,
    /// <summary>
    /// The Windows 10 Mixed reality SDK provided by the Universal Windows Platform (UWP), for Immersive MR headsets and HoloLens.
    /// </summary>
    WindowsMR,
    /// <summary>
    /// The OpenVR platform provided by Unity (does not support the downloadable SteamVR SDK).
    /// </summary>
    OpenVR,
    /// <summary>
    /// The OpenXR platform. SDK to be determined once released.
    /// </summary>
    OpenXR
}
```

### <a name="review-enum-use-for-bitfields"></a><span data-ttu-id="5c27d-251">Examiner l’utilisation des énumérations pour les champs binaires</span><span class="sxs-lookup"><span data-stu-id="5c27d-251">Review enum use for bitfields</span></span>

<span data-ttu-id="5c27d-252">S’il existe une possibilité pour une énumération d’exiger plusieurs États comme valeur, par exemple, droitier = gauche & droite.</span><span class="sxs-lookup"><span data-stu-id="5c27d-252">If there is a possibility for an enum to require multiple states as a value, e.g. Handedness = Left & Right.</span></span> <span data-ttu-id="5c27d-253">Ensuite, l’énumération doit être décorée correctement avec indicateurs pour permettre son utilisation correcte</span><span class="sxs-lookup"><span data-stu-id="5c27d-253">Then the Enum needs to be decorated correctly with BitFlags to enable it to be used correctly</span></span>

<span data-ttu-id="5c27d-254">Le fichier droitier. cs a une implémentation concrète pour cela</span><span class="sxs-lookup"><span data-stu-id="5c27d-254">The Handedness.cs file has a concrete implementation for this</span></span>

### <a name="dont"></a><span data-ttu-id="5c27d-255">À ne pas faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-255">Don't</span></span>

```c#
public enum Handedness
{
    None,
    Left,
    Right
}
```

### <a name="do"></a><span data-ttu-id="5c27d-256">À faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-256">Do</span></span>

```c#
[Flags]
public enum Handedness
{
    None = 0 << 0,
    Left = 1 << 0,
    Right = 1 << 1,
    Both = Left | Right
}
```

### <a name="hard-coded-file-paths"></a><span data-ttu-id="5c27d-257">Chemins d’accès aux fichiers codés en dur</span><span class="sxs-lookup"><span data-stu-id="5c27d-257">Hard-coded file paths</span></span>

<span data-ttu-id="5c27d-258">Lors de la génération de chemins d’accès de fichier de chaîne, et en particulier l’écriture de chemins d’accès de chaîne codés en dur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5c27d-258">When generating string file paths, and in particular writing hard-coded string paths, do the following:</span></span>

1. <span data-ttu-id="5c27d-259">Utilisez des [ `Path` API](/dotnet/api/system.io.path?preserve-view=true&view=netframework-4.8) C# dans la mesure du possible, telles que `Path.Combine` ou `Path.GetFullPath` .</span><span class="sxs-lookup"><span data-stu-id="5c27d-259">Use C#'s [`Path` APIs](/dotnet/api/system.io.path?preserve-view=true&view=netframework-4.8) whenever possible such as `Path.Combine` or `Path.GetFullPath`.</span></span>
1. <span data-ttu-id="5c27d-260">Utilisez/ou à la [`Path.DirectorySeparatorChar`](/dotnet/api/system.io.path.directoryseparatorchar?preserve-view=true&view=netframework-4.8) place de \ ou \\ \\ .</span><span class="sxs-lookup"><span data-stu-id="5c27d-260">Use / or [`Path.DirectorySeparatorChar`](/dotnet/api/system.io.path.directoryseparatorchar?preserve-view=true&view=netframework-4.8) instead of \ or \\\\.</span></span>

<span data-ttu-id="5c27d-261">ces étapes permettent de s’assurer que MRTK fonctionne sur les systèmes Windows et Unix.</span><span class="sxs-lookup"><span data-stu-id="5c27d-261">These steps ensure that MRTK works on both Windows and Unix-based systems.</span></span>

### <a name="dont"></a><span data-ttu-id="5c27d-262">À ne pas faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-262">Don't</span></span>

```c#
private const string FilePath = "MyPath\\to\\a\\file.txt";
private const string OtherFilePath = "MyPath\to\a\file.txt";

string filePath = myVarRootPath + myRelativePath;
```

### <a name="do"></a><span data-ttu-id="5c27d-263">À faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-263">Do</span></span>

```c#
private const string FilePath = "MyPath/to/a/file.txt";
private const string OtherFilePath = "folder{Path.DirectorySeparatorChar}file.txt";

string filePath = Path.Combine(myVarRootPath,myRelativePath);

// Path.GetFullPath() will return the full length path of provided with correct system directory separators
string cleanedFilePath = Path.GetFullPath(unknownSourceFilePath);
```

## <a name="best-practices-including-unity-recommendations"></a><span data-ttu-id="5c27d-264">Meilleures pratiques, y compris les recommandations Unity</span><span class="sxs-lookup"><span data-stu-id="5c27d-264">Best practices, including Unity recommendations</span></span>

<span data-ttu-id="5c27d-265">Certaines des plates-formes cibles de ce projet nécessitent de prendre en compte les performances.</span><span class="sxs-lookup"><span data-stu-id="5c27d-265">Some of the target platforms of this project require to take performance into consideration.</span></span> <span data-ttu-id="5c27d-266">En tenant compte de cela, soyez toujours prudent quand vous allouez de la mémoire dans du code fréquemment appelé dans des boucles ou des algorithmes de mise à jour serrés.</span><span class="sxs-lookup"><span data-stu-id="5c27d-266">With this in mind always be careful when allocating memory in frequently called code in tight update loops or algorithms.</span></span>

### <a name="encapsulation"></a><span data-ttu-id="5c27d-267">Encapsulation</span><span class="sxs-lookup"><span data-stu-id="5c27d-267">Encapsulation</span></span>

<span data-ttu-id="5c27d-268">Utilisez toujours les champs privés et les propriétés publiques si l’accès au champ est nécessaire à partir de l’extérieur de la classe ou du struct.</span><span class="sxs-lookup"><span data-stu-id="5c27d-268">Always use private fields and public properties if access to the field is needed from outside the class or struct.</span></span>  <span data-ttu-id="5c27d-269">Veillez à colocaliser le champ privé et la propriété publique.</span><span class="sxs-lookup"><span data-stu-id="5c27d-269">Be sure to co-locate the private field and the public property.</span></span> <span data-ttu-id="5c27d-270">Cela permet de mieux voir, d’un seul coup d’œil, ce qui stocke la propriété et que le champ est modifiable par le script.</span><span class="sxs-lookup"><span data-stu-id="5c27d-270">This makes it easier to see, at a glance, what backs the property and that the field is modifiable by script.</span></span>

> [!NOTE]
> <span data-ttu-id="5c27d-271">La seule exception concerne les structures de données qui requièrent que les champs soient sérialisés par le `JsonUtility` , où une classe de données doit avoir tous les champs publics pour que la sérialisation fonctionne.</span><span class="sxs-lookup"><span data-stu-id="5c27d-271">The only exception to this is for data structures that require the fields to be serialized by the `JsonUtility`, where a data class is required to have all public fields for the serialization to work.</span></span>

#### <a name="dont"></a><span data-ttu-id="5c27d-272">À ne pas faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-272">Don't</span></span>

```c#
private float myValue1;
private float myValue2;

public float MyValue1
{
    get{ return myValue1; }
    set{ myValue1 = value }
}

public float MyValue2
{
    get{ return myValue2; }
    set{ myValue2 = value }
}
```

#### <a name="do"></a><span data-ttu-id="5c27d-273">À faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-273">Do</span></span>

```c#
// Enable field to be configurable in the editor and available externally to other scripts (field is correctly serialized in Unity)
[SerializeField]
[ToolTip("If using a tooltip, the text should match the public property's summary documentation, if appropriate.")]
private float myValue; // <- Notice we co-located the backing field above our corresponding property.

/// <summary>
/// If using a tooltip, the text should match the public property's summary documentation, if appropriate.
/// </summary>
public float MyValue
{
    get => myValue;
    set => myValue = value;
}

/// <summary>
/// Getter/Setters not wrapping a value directly should contain documentation comments just as public functions would
/// </summary>
public float AbsMyValue
{
    get
    {
        if (MyValue < 0)
        {
            return -MyValue;
        }

        return MyValue
    }
}
```

### <a name="cache-values-and-serialize-them-in-the-sceneprefab-whenever-possible"></a><span data-ttu-id="5c27d-274">Mettre en cache les valeurs et les sérialiser dans Scene/Prefab chaque fois que cela est possible</span><span class="sxs-lookup"><span data-stu-id="5c27d-274">Cache values and serialize them in the scene/prefab whenever possible</span></span>

<span data-ttu-id="5c27d-275">avec la HoloLens à l’esprit, il est préférable d’optimiser les performances et les références de cache dans la scène ou prefab pour limiter les allocations de mémoire du runtime.</span><span class="sxs-lookup"><span data-stu-id="5c27d-275">With the HoloLens in mind, it's best to optimize for performance and cache references in the scene or prefab to limit runtime memory allocations.</span></span>

#### <a name="dont"></a><span data-ttu-id="5c27d-276">À ne pas faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-276">Don't</span></span>

```c#
void Update()
{
    gameObject.GetComponent<Renderer>().Foo(Bar);
}
```

#### <a name="do"></a><span data-ttu-id="5c27d-277">À faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-277">Do</span></span>

```c#
[SerializeField] // To enable setting the reference in the inspector.
private Renderer myRenderer;

private void Awake()
{
    // If you didn't set it in the inspector, then we cache it on awake.
    if (myRenderer == null)
    {
        myRenderer = gameObject.GetComponent<Renderer>();
    }
}

private void Update()
{
    myRenderer.Foo(Bar);
}
```

### <a name="cache-references-to-materials-do-not-call-the-material-each-time"></a><span data-ttu-id="5c27d-278">Mettre en cache des références à des matériaux, n’appelez pas « . Material » à chaque fois</span><span class="sxs-lookup"><span data-stu-id="5c27d-278">Cache references to materials, do not call the ".material" each time</span></span>

<span data-ttu-id="5c27d-279">Unity crée un nouveau matériau chaque fois que vous utilisez « . Material », ce qui entraîne une fuite de mémoire si elle n’est pas nettoyée correctement.</span><span class="sxs-lookup"><span data-stu-id="5c27d-279">Unity will create a new material each time you use ".material", which will cause a memory leak if not cleaned up properly.</span></span>

#### <a name="dont"></a><span data-ttu-id="5c27d-280">À ne pas faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-280">Don't</span></span>

```c#
public class MyClass
{
    void Update()
    {
        Material myMaterial = GetComponent<Renderer>().material;
        myMaterial.SetColor("_Color", Color.White);
    }
}
```

#### <a name="do"></a><span data-ttu-id="5c27d-281">À faire</span><span class="sxs-lookup"><span data-stu-id="5c27d-281">Do</span></span>

```c#
// Private references for use inside the class only
public class MyClass
{
    private Material cachedMaterial;

    private void Awake()
    {
        cachedMaterial = GetComponent<Renderer>().material;
    }

    void Update()
    {
        cachedMaterial.SetColor("_Color", Color.White);
    }

    private void OnDestroy()
    {
        Destroy(cachedMaterial);
    }
}
```

> [!NOTE]
> <span data-ttu-id="5c27d-282">Vous pouvez également utiliser la propriété « SharedMaterial » d’Unity qui ne crée pas de nouveau matériau chaque fois qu’elle est référencée.</span><span class="sxs-lookup"><span data-stu-id="5c27d-282">Alternatively, use Unity's "SharedMaterial" property which does not create a new material each time it is referenced.</span></span>

### <a name="use-platform-dependent-compilation-to-ensure-the-toolkit-wont-break-the-build-on-another-platform"></a><span data-ttu-id="5c27d-283">utilisez la [compilation dépendante](https://docs.unity3d.com/Manual/PlatformDependentCompilation.html) de la plateforme pour vous assurer que la Shared Computer Toolkit n’interrompt pas la génération sur une autre plateforme</span><span class="sxs-lookup"><span data-stu-id="5c27d-283">Use [platform dependent compilation](https://docs.unity3d.com/Manual/PlatformDependentCompilation.html) to ensure the Toolkit won't break the build on another platform</span></span>

- <span data-ttu-id="5c27d-284">Utilisez afin `WINDOWS_UWP` d’utiliser des API non Unity spécifiques à UWP.</span><span class="sxs-lookup"><span data-stu-id="5c27d-284">Use `WINDOWS_UWP` in order to use UWP-specific, non-Unity APIs.</span></span> <span data-ttu-id="5c27d-285">Cela les empêchera d’essayer de s’exécuter dans l’éditeur ou sur des plateformes non prises en charge.</span><span class="sxs-lookup"><span data-stu-id="5c27d-285">This will prevent them from trying to run in the Editor or on unsupported platforms.</span></span> <span data-ttu-id="5c27d-286">Cela équivaut à `UNITY_WSA && !UNITY_EDITOR` et doit être utilisé en faveur de.</span><span class="sxs-lookup"><span data-stu-id="5c27d-286">This is equivalent to `UNITY_WSA && !UNITY_EDITOR` and should be used in favor of.</span></span>
- <span data-ttu-id="5c27d-287">Utilisez `UNITY_WSA` pour utiliser des API Unity spécifiques à UWP, telles que l' `UnityEngine.XR.WSA` espace de noms.</span><span class="sxs-lookup"><span data-stu-id="5c27d-287">Use `UNITY_WSA` to use UWP-specific Unity APIs, such as the `UnityEngine.XR.WSA` namespace.</span></span> <span data-ttu-id="5c27d-288">Cette opération s’exécute dans l’éditeur lorsque la plateforme est définie sur UWP, ainsi que dans les applications UWP générées.</span><span class="sxs-lookup"><span data-stu-id="5c27d-288">This will run in the Editor when the platform is set to UWP, as well as in built UWP apps.</span></span>

<span data-ttu-id="5c27d-289">Ce graphique peut vous aider à décider de ce qui `#if` doit être utilisé, en fonction de vos cas d’usage et des paramètres de génération attendus.</span><span class="sxs-lookup"><span data-stu-id="5c27d-289">This chart can help you decide which `#if` to use, depending on your use cases and the build settings you expect.</span></span>

|<span data-ttu-id="5c27d-290">Plateforme</span><span class="sxs-lookup"><span data-stu-id="5c27d-290">Platform</span></span> | <span data-ttu-id="5c27d-291">IL2CPP UWP</span><span class="sxs-lookup"><span data-stu-id="5c27d-291">UWP IL2CPP</span></span> | <span data-ttu-id="5c27d-292">.NET UWP</span><span class="sxs-lookup"><span data-stu-id="5c27d-292">UWP .NET</span></span> | <span data-ttu-id="5c27d-293">Éditeur</span><span class="sxs-lookup"><span data-stu-id="5c27d-293">Editor</span></span> |
| --- | --- | --- | --- |
| `UNITY_EDITOR` | <span data-ttu-id="5c27d-294">Faux</span><span class="sxs-lookup"><span data-stu-id="5c27d-294">False</span></span> | <span data-ttu-id="5c27d-295">False</span><span class="sxs-lookup"><span data-stu-id="5c27d-295">False</span></span> | <span data-ttu-id="5c27d-296">True</span><span class="sxs-lookup"><span data-stu-id="5c27d-296">True</span></span> |
| `UNITY_WSA` | <span data-ttu-id="5c27d-297">True</span><span class="sxs-lookup"><span data-stu-id="5c27d-297">True</span></span> | <span data-ttu-id="5c27d-298">True</span><span class="sxs-lookup"><span data-stu-id="5c27d-298">True</span></span> | <span data-ttu-id="5c27d-299">True</span><span class="sxs-lookup"><span data-stu-id="5c27d-299">True</span></span> |
| `WINDOWS_UWP` | <span data-ttu-id="5c27d-300">True</span><span class="sxs-lookup"><span data-stu-id="5c27d-300">True</span></span> | <span data-ttu-id="5c27d-301">True</span><span class="sxs-lookup"><span data-stu-id="5c27d-301">True</span></span> | <span data-ttu-id="5c27d-302">False</span><span class="sxs-lookup"><span data-stu-id="5c27d-302">False</span></span> |
| `UNITY_WSA && !UNITY_EDITOR` | <span data-ttu-id="5c27d-303">True</span><span class="sxs-lookup"><span data-stu-id="5c27d-303">True</span></span> | <span data-ttu-id="5c27d-304">True</span><span class="sxs-lookup"><span data-stu-id="5c27d-304">True</span></span> | <span data-ttu-id="5c27d-305">False</span><span class="sxs-lookup"><span data-stu-id="5c27d-305">False</span></span> |
| `ENABLE_WINMD_SUPPORT` | <span data-ttu-id="5c27d-306">True</span><span class="sxs-lookup"><span data-stu-id="5c27d-306">True</span></span> | <span data-ttu-id="5c27d-307">True</span><span class="sxs-lookup"><span data-stu-id="5c27d-307">True</span></span> | <span data-ttu-id="5c27d-308">Faux</span><span class="sxs-lookup"><span data-stu-id="5c27d-308">False</span></span> |
| `NETFX_CORE` | <span data-ttu-id="5c27d-309">False</span><span class="sxs-lookup"><span data-stu-id="5c27d-309">False</span></span> | <span data-ttu-id="5c27d-310">True</span><span class="sxs-lookup"><span data-stu-id="5c27d-310">True</span></span> | <span data-ttu-id="5c27d-311">Faux</span><span class="sxs-lookup"><span data-stu-id="5c27d-311">False</span></span> |

### <a name="prefer-datetimeutcnow-over-datetimenow"></a><span data-ttu-id="5c27d-312">Préférez DateTime. UtcNow à DateTime. Now</span><span class="sxs-lookup"><span data-stu-id="5c27d-312">Prefer DateTime.UtcNow over DateTime.Now</span></span>

<span data-ttu-id="5c27d-313">DateTime. UtcNow est plus rapide que DateTime. Now.</span><span class="sxs-lookup"><span data-stu-id="5c27d-313">DateTime.UtcNow is faster than DateTime.Now.</span></span> <span data-ttu-id="5c27d-314">Dans les enquêtes de performances précédentes, nous avons découvert que l’utilisation de DateTime. ajoute désormais une surcharge significative en particulier lorsqu’elle est utilisée dans la boucle Update ().</span><span class="sxs-lookup"><span data-stu-id="5c27d-314">In previous performance investigations we've found that using DateTime.Now adds significant overhead especially when used in the Update() loop.</span></span> <span data-ttu-id="5c27d-315">[D’autres ont rencontré le même problème](https://stackoverflow.com/questions/1561791/optimizing-alternatives-to-datetime-now).</span><span class="sxs-lookup"><span data-stu-id="5c27d-315">[Others have hit the same issue](https://stackoverflow.com/questions/1561791/optimizing-alternatives-to-datetime-now).</span></span>

<span data-ttu-id="5c27d-316">Préférez l’utilisation de DateTime. UtcNow, sauf si vous avez réellement besoin des heures localisées (il est possible que vous souhaitiez afficher l’heure actuelle dans le fuseau horaire de l’utilisateur).</span><span class="sxs-lookup"><span data-stu-id="5c27d-316">Prefer using DateTime.UtcNow unless you actually need the localized times (a legitimate reason may be you wanting to show the current time in the user's time zone).</span></span> <span data-ttu-id="5c27d-317">Si vous traitez des temps relatifs (par exemple, le delta entre une dernière mise à jour et maintenant), il est préférable d’utiliser DateTime. UtcNow pour éviter la surcharge liée à la réalisation de conversions de fuseau horaire.</span><span class="sxs-lookup"><span data-stu-id="5c27d-317">If you are dealing with relative times (i.e. the delta between some last update and now), it's best to use DateTime.UtcNow to avoid the overhead of doing timezone conversions.</span></span>

## <a name="powershell-coding-conventions"></a><span data-ttu-id="5c27d-318">Conventions de codage PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c27d-318">PowerShell coding conventions</span></span>

<span data-ttu-id="5c27d-319">Un sous-ensemble du code base MRTK utilise PowerShell pour l’infrastructure de pipeline et divers scripts et utilitaires.</span><span class="sxs-lookup"><span data-stu-id="5c27d-319">A subset of the MRTK codebase uses PowerShell for pipeline infrastructure and various scripts and utilities.</span></span> <span data-ttu-id="5c27d-320">Le nouveau code PowerShell doit suivre le [style PoshCode](https://poshcode.gitbooks.io/powershell-practice-and-style/).</span><span class="sxs-lookup"><span data-stu-id="5c27d-320">New PowerShell code should follow the [PoshCode style](https://poshcode.gitbooks.io/powershell-practice-and-style/).</span></span>

## <a name="see-also"></a><span data-ttu-id="5c27d-321">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5c27d-321">See also</span></span>

 [<span data-ttu-id="5c27d-322">Conventions de codage C# de MSDN</span><span class="sxs-lookup"><span data-stu-id="5c27d-322">C# coding conventions from MSDN</span></span>](/dotnet/csharp/programming-guide/inside-a-program/coding-conventions)
