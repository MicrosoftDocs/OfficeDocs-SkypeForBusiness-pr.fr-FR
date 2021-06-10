---
title: Stratégies de contrôle AppLocker
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: Découvrez comment activer l’application Teams client de bureau avec des stratégies de contrôle d’application AppLocker.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d6e6040956ba5e5469076b4fbbab337f58268c68
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120846"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="959e2-103">Stratégies de contrôle d’application AppLocker dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="959e2-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="959e2-104">Cet article explique comment activer l’application cliente Teams bureau à l’application AppLocker.</span><span class="sxs-lookup"><span data-stu-id="959e2-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="959e2-105">L’utilisation d’AppLocker est conçue pour restreindre l’exécution des programmes et scripts par les utilisateurs non administratifs.</span><span class="sxs-lookup"><span data-stu-id="959e2-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="959e2-106">Pour plus d’informations et des conseils sur AppLocker, voir [Qu’est-ce qu’AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)?</span><span class="sxs-lookup"><span data-stu-id="959e2-106">For more information and guidance on AppLocker, see [What is AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="959e2-107">Le processus d’activation Teams appLocker nécessite la création de stratégies d’activation de listes autorises basées sur AppLocker.</span><span class="sxs-lookup"><span data-stu-id="959e2-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based allow listing policies.</span></span> <span data-ttu-id="959e2-108">Les stratégies sont créées avec un logiciel de gestion des stratégies de groupe et/ou l’utilisation d’Windows PowerShell cmdlets pour AppLocker (voir la référence technique [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) pour plus d’informations).</span><span class="sxs-lookup"><span data-stu-id="959e2-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="959e2-109">La stratégie AppLocker est enregistrée au format XML et peut être modifiée avec n’importe quel éditeur de texte ou XML.</span><span class="sxs-lookup"><span data-stu-id="959e2-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-allow-list-with-applocker"></a><span data-ttu-id="959e2-110">Teams liste d’applications avec AppLocker</span><span class="sxs-lookup"><span data-stu-id="959e2-110">Teams allow list with AppLocker</span></span>

<span data-ttu-id="959e2-111">Les règles AppLocker sont organisées en collections de règles.</span><span class="sxs-lookup"><span data-stu-id="959e2-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="959e2-112">Les règles AppLocker s’appliquent à l’application ciblée et elles sont les composants qui font partie de la stratégie AppLocker.</span><span class="sxs-lookup"><span data-stu-id="959e2-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="959e2-113">Pour autoriser les Teams, nous vous recommandons d’utiliser les règles de [condition](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) de l’éditeur, car tous Teams fichiers d’application sont signés numériquement.</span><span class="sxs-lookup"><span data-stu-id="959e2-113">To allow Teams, we recommend that you use the [publisher condition rules](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="959e2-114">Nous vous déconseillons d’utiliser des règles de chemin d’accès, car le Teams d’installation peut être accessible par les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="959e2-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="959e2-115">Par ailleurs, nous vous déconseillons d’utiliser des règles de hachage, car elles doivent être mises à jour chaque fois que l’Teams client est mise à jour.</span><span class="sxs-lookup"><span data-stu-id="959e2-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="959e2-116">Dans Teams fichiers exécutables du bureau sont signés numériquement, la condition de l’éditeur identifie un fichier d’application en fonction de sa signature numérique et des attributs de version incorporés.</span><span class="sxs-lookup"><span data-stu-id="959e2-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="959e2-117">La signature numérique contient des informations sur la société qui a créé le fichier d’application (l’éditeur).</span><span class="sxs-lookup"><span data-stu-id="959e2-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="959e2-118">Les informations de version, obtenues à partir de la ressource binaire, incluent le nom du produit dont fait partie le fichier et le numéro de version du fichier d’application.</span><span class="sxs-lookup"><span data-stu-id="959e2-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="959e2-119">Exemples de règles de condition de l’éditeur</span><span class="sxs-lookup"><span data-stu-id="959e2-119">Example of publisher condition rules</span></span>

<span data-ttu-id="959e2-120">Pour l’Teams client (tous les fichiers, toutes les versions) ajoutez ce qui suit aux règles exécutables & DLL :</span><span class="sxs-lookup"><span data-stu-id="959e2-120">For the Teams client app (all files, all versions) add the following to the Executable Rules & DLL Rules:</span></span>

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a><span data-ttu-id="959e2-121">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="959e2-121">Related topics</span></span>
<span data-ttu-id="959e2-122">[Qu’est-ce que AppLocker ?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Référence technique AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="959e2-122">[What is AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>