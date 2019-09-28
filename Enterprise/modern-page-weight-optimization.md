---
title: Optimiser le poids des pages de sites modernes SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/18/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: Adm_O365
ms.reviewer: sstewart
search.appverid:
- MET150
description: Découvrez comment optimiser le poids des pages de sites modernes SharePoint Online.
ms.openlocfilehash: 5e2231468363f58faeac1d7b21e06cd4fa790cf8
ms.sourcegitcommit: c7764503422922cb333b05d54e8ebbdb894df2f9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/18/2019
ms.locfileid: "37028211"
---
# <a name="optimize-page-weight-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="60bd7-103">Optimiser le poids des pages de sites modernes SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="60bd7-103">Optimize page weight in SharePoint Online modern site pages</span></span>

<span data-ttu-id="60bd7-104">Les pages de sites modernes SharePoint Online contiennent du code sérialisé nécessaire pour restituer le contenu de la page, y compris les images, le texte, les objets dans la zone de contenu sous les barres de navigation/commandes et d’autres codes HTML qui constituent la structure de la page.</span><span class="sxs-lookup"><span data-stu-id="60bd7-104">SharePoint Online modern site pages contain serialized code that is required to render page content of the page, including images, text, objects in the content area underneath navigation/command bars and other HTML code that forms the framework of the page.</span></span> <span data-ttu-id="60bd7-105">Le poids de pages est une mesure de ce code HTML et doit être limitée afin de garantir des temps de chargement optimaux pour les pages.</span><span class="sxs-lookup"><span data-stu-id="60bd7-105">Page weight is a measurement of this HTML code, and should be limited to ensure optimal page load times.</span></span>

<span data-ttu-id="60bd7-106">Cet article vous permet de comprendre comment réduire le poids des pages de vos sites modernes.</span><span class="sxs-lookup"><span data-stu-id="60bd7-106">This article will help you understand how to reduce page weight in your modern site pages.</span></span>

>[!NOTE]
><span data-ttu-id="60bd7-107">Pour plus d’informations sur les performances dans les portails modernes SharePoint Online, consultez [Performances offertes par l’expérience moderne de SharePoint](https://docs.microsoft.com/fr-FR/sharepoint/modern-experience-performance).</span><span class="sxs-lookup"><span data-stu-id="60bd7-107">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](https://docs.microsoft.com/fr-FR/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-weight"></a><span data-ttu-id="60bd7-108">Utiliser l’outil Diagnostic de page pour SharePoint pour analyser le poids des pages</span><span class="sxs-lookup"><span data-stu-id="60bd7-108">Use the Page Diagnostics for SharePoint tool to analyze page weight</span></span>

<span data-ttu-id="60bd7-109">L’outil **Diagnostic de page pour SharePoint** est une extension de navigateur pour Chrome et [Microsoft Edge version 77 ou ultérieure](https://www.microsoftedgeinsider.com/en-us/download?form=MI13E8&OCID=MI13E8) que vous pouvez utiliser pour analyser les pages de sites de publication modernes et classiques SharePoint.</span><span class="sxs-lookup"><span data-stu-id="60bd7-109">The **Page Diagnostics for SharePoint tool** is a browser extension for Chrome and [Microsoft Edge version 77 or later](https://www.microsoftedgeinsider.com/en-us/download?form=MI13E8&OCID=MI13E8) you can use to analyze SharePoint both modern and classic publishing site pages.</span></span> <span data-ttu-id="60bd7-110">L’outil fournit un rapport pour chaque page analysée montrant comment la page se comporte par rapport à un ensemble défini de critères de performance.</span><span class="sxs-lookup"><span data-stu-id="60bd7-110">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="60bd7-111">Pour installer et découvrir l’outil Diagnostic de page pour SharePoint, consultez [Utiliser l’outil Diagnostic de page pour SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="60bd7-111">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

<span data-ttu-id="60bd7-112">Lorsque vous analysez une page de site SharePoint avec l’outil Diagnostic de page pour SharePoint, vous pouvez voir des informations sur la page dans les résultats **Poids de pages inférieur à 500 Ko** du volet _Tests de diagnostic_.</span><span class="sxs-lookup"><span data-stu-id="60bd7-112">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about page in the **Page weight under 500KB** result of the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="60bd7-113">Le résultat s’affiche en vert si le poids de la page est inférieur à la valeur de référence et rouge si le poids de la page dépasse la valeur de référence.</span><span class="sxs-lookup"><span data-stu-id="60bd7-113">The result will appear in green if the page weight is under the baseline value, and red if the page weight exceeds the baseline value.</span></span>

<span data-ttu-id="60bd7-114">Les résultats possibles sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="60bd7-114">Possible results include:</span></span>

- <span data-ttu-id="60bd7-115">**Attention requise** (rouge) : le poids de la page dépasse 500 Ko</span><span class="sxs-lookup"><span data-stu-id="60bd7-115">**Attention required** (red): Page weight exceeds 500KB</span></span>
- <span data-ttu-id="60bd7-116">**Aucune action requise** (vert) : le poids de la page est inférieur à 500 Ko</span><span class="sxs-lookup"><span data-stu-id="60bd7-116">**No action required** (green): Page weight is under 500KB</span></span>

<span data-ttu-id="60bd7-117">Si le résultat **Poids de page inférieur à 500 Ko** apparaît dans la section **Attention requise**, vous pouvez cliquer sur le résultat pour afficher les détails.</span><span class="sxs-lookup"><span data-stu-id="60bd7-117">If the **Page weight under 500KB** result appears in the **Attention required** section, you can click the result for details.</span></span>

![Résultats de requêtes à SharePoint](media/modern-portal-optimization/pagediag-page-weight.png)

## <a name="remediate-page-weight-issues"></a><span data-ttu-id="60bd7-119">Résoudre les problèmes de poids de pages</span><span class="sxs-lookup"><span data-stu-id="60bd7-119">Remediate page weight issues</span></span>

<span data-ttu-id="60bd7-120">Si le poids des pages dépasse 500 Ko, vous pouvez améliorer le temps de chargement général des pages en réduisant le nombre de composants WebPart et en réduisant le contenu de la page dans la mesure appropriée.</span><span class="sxs-lookup"><span data-stu-id="60bd7-120">If page weight exceeds 500KB, you can improve overall page load time by reducing the number of web parts and limiting page content to an appropriate degree.</span></span>

<span data-ttu-id="60bd7-121">Les recommandations générales pour réduire le poids des pages incluent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="60bd7-121">General guidance for reducing page weight includes:</span></span>

- <span data-ttu-id="60bd7-122">Limitez le contenu de la page à un volume raisonnable et utilisez plusieurs pages pour le contenu connexe.</span><span class="sxs-lookup"><span data-stu-id="60bd7-122">Limit the page content to a reasonable amount and use multiple pages for related content.</span></span>
- <span data-ttu-id="60bd7-123">Réduisez l’utilisation des composants WebPart comportant de grands conteneurs de propriétés.</span><span class="sxs-lookup"><span data-stu-id="60bd7-123">Minimize the use of web parts that have large property bags.</span></span>
- <span data-ttu-id="60bd7-124">Utilisez les vues cumulatives non interactives lorsque c’est possible.</span><span class="sxs-lookup"><span data-stu-id="60bd7-124">Use non-interactive rollup views when possible.</span></span>
- <span data-ttu-id="60bd7-125">Optimisez la taille des images en redimensionnant les images de façon appropriée en utilisant des formats d’images compressés et en vous assurant qu’elles sont téléchargées à partir d’un réseau de distribution de contenu.</span><span class="sxs-lookup"><span data-stu-id="60bd7-125">Optimize image sizes by sizing images appropriately, using compressed image formats and ensuring that they are downloaded from a CDN.</span></span>

<span data-ttu-id="60bd7-126">Vous trouverez des conseils supplémentaires pour limiter le poids des pages dans l’article suivant :</span><span class="sxs-lookup"><span data-stu-id="60bd7-126">You can find additional guidance for limiting page weight in the following article:</span></span>

- [<span data-ttu-id="60bd7-127">Optimiser les performances des pages dans SharePoint</span><span class="sxs-lookup"><span data-stu-id="60bd7-127">Optimize page performance in SharePoint</span></span>](https://docs.microsoft.com/fr-FR/sharepoint/dev/general-development/optimize-page-performance-in-sharepoint)

<span data-ttu-id="60bd7-128">Avant d’apporter des révisions de page pour résoudre les problèmes de performances, notez le temps de chargement des pages dans les résultats de l’analyse.</span><span class="sxs-lookup"><span data-stu-id="60bd7-128">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="60bd7-129">Exécutez à nouveau l’outil après votre révision pour déterminer si le nouveau résultat est inclus dans la norme de référence et vérifier le nouveau temps de chargement des pages pour voir s’il y a eu une amélioration.</span><span class="sxs-lookup"><span data-stu-id="60bd7-129">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Résultats du temps de chargement des pages](media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="60bd7-131">Le temps de chargement des pages peut varier en fonction de nombreux facteurs tels que la charge réseau, l’heure de la journée et d’autres conditions transitoires.</span><span class="sxs-lookup"><span data-stu-id="60bd7-131">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="60bd7-132">Vous devez tester le temps de chargement des pages plusieurs fois avant et après avoir apporté des modifications pour vous aider à faire la moyenne des résultats.</span><span class="sxs-lookup"><span data-stu-id="60bd7-132">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="60bd7-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="60bd7-133">Related topics</span></span>

[<span data-ttu-id="60bd7-134">Optimisation des performances SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="60bd7-134">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="60bd7-135">Optimisation des performances Office 365</span><span class="sxs-lookup"><span data-stu-id="60bd7-135">Tune Office 365 performance</span></span>](tune-office-365-performance.md)

[<span data-ttu-id="60bd7-136">Performances offertes par l’expérience moderne de SharePoint</span><span class="sxs-lookup"><span data-stu-id="60bd7-136">Performance in the modern SharePoint experience</span></span>](https://docs.microsoft.com/fr-FR/sharepoint/modern-experience-performance.md)

[<span data-ttu-id="60bd7-137">Réseaux de distribution de contenu</span><span class="sxs-lookup"><span data-stu-id="60bd7-137">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="60bd7-138">Utilisation du réseau de distribution de contenu Office 365 avec SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="60bd7-138">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-office-365-cdn-with-spo.md)