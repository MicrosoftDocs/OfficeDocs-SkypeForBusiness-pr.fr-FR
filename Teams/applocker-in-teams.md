---
title: Stratégies de contrôle AppLocker
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: Apprenez à activer l’application cliente de bureau teams avec des stratégies de contrôle d’application AppLocker.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3bcb75eb28730b4387ebcee0be869f1f91cc31c5
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137424"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="d6ae7-103">Stratégies de contrôle d’application AppLocker dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="d6ae7-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="d6ae7-104">Cet article explique comment activer l’application Microsoft teams cliente de bureau avec des stratégies de contrôle d’application AppLocker.</span><span class="sxs-lookup"><span data-stu-id="d6ae7-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="d6ae7-105">L’utilisation de AppLocker a pour but de limiter l’exécution du programme et du script par des utilisateurs non administrateurs.</span><span class="sxs-lookup"><span data-stu-id="d6ae7-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="d6ae7-106">Pour plus d’informations et des instructions sur AppLocker, voir [qu’est-ce que AppLocker ?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span><span class="sxs-lookup"><span data-stu-id="d6ae7-106">For more information and guidance on AppLocker, see [What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="d6ae7-107">Le processus d’activation d’une équipe avec AppLocker nécessite la création de stratégies de création de listes de personnes basées sur AppLocker.</span><span class="sxs-lookup"><span data-stu-id="d6ae7-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based whitelisting policies.</span></span> <span data-ttu-id="d6ae7-108">Les stratégies sont créées à l’aide d’un logiciel de gestion des stratégies de groupe et/ou de l’utilisation des cmdlets Windows PowerShell pour AppLocker (voir [référence technique AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) pour plus d’informations).</span><span class="sxs-lookup"><span data-stu-id="d6ae7-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="d6ae7-109">La stratégie AppLocker est enregistrée au format XML et peut être modifiée à l’aide d’un éditeur de texte ou XML.</span><span class="sxs-lookup"><span data-stu-id="d6ae7-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-whitelisting-with-applocker"></a><span data-ttu-id="d6ae7-110">Teams, création de listes d’AppLocker</span><span class="sxs-lookup"><span data-stu-id="d6ae7-110">Teams whitelisting with AppLocker</span></span>

<span data-ttu-id="d6ae7-111">Les règles AppLocker sont organisées en collections de règles.</span><span class="sxs-lookup"><span data-stu-id="d6ae7-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="d6ae7-112">Les règles AppLocker s’appliquent à l’application ciblée et sont les composants qui constituent la stratégie AppLocker.</span><span class="sxs-lookup"><span data-stu-id="d6ae7-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="d6ae7-113">Pour les équipes de liste blanche, nous vous conseillons d’utiliser les [règles de condition Publisher](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) puisque tous les fichiers d’application teams sont signés numériquement.</span><span class="sxs-lookup"><span data-stu-id="d6ae7-113">To whitelist Teams, we recommend that you use the [publisher condition rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="d6ae7-114">Nous déconseillons l’utilisation de règles de chemin d’accès, car le répertoire d’installation de teams est accessible par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d6ae7-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="d6ae7-115">Par ailleurs, nous ne recommandons pas l’utilisation des règles de hachage, car elles doivent être mises à jour à chaque mise à jour de l’application cliente Teams.</span><span class="sxs-lookup"><span data-stu-id="d6ae7-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="d6ae7-116">Dans la mesure où les fichiers exécutable de bureau teams sont signés numériquement, la condition d’éditeur identifie un fichier d’application en fonction de sa signature numérique et des attributs de version incorporés.</span><span class="sxs-lookup"><span data-stu-id="d6ae7-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="d6ae7-117">La signature numérique contient des informations sur la société qui a créé le fichier d’application (l’éditeur).</span><span class="sxs-lookup"><span data-stu-id="d6ae7-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="d6ae7-118">Les informations de version, obtenues à partir de la ressource binaire, incluent le nom du produit dont fait partie le fichier et le numéro de version du fichier d’application.</span><span class="sxs-lookup"><span data-stu-id="d6ae7-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="d6ae7-119">Exemple de règles de condition Publisher</span><span class="sxs-lookup"><span data-stu-id="d6ae7-119">Example of publisher condition rules</span></span>

<span data-ttu-id="d6ae7-120">Pour l’application client Teams (tous les fichiers, toutes les versions), ajoutez les éléments suivants aux règles d’exécution & règles de DLL :</span><span class="sxs-lookup"><span data-stu-id="d6ae7-120">For the Teams client app (all files, all versions) add the following to the Executable Rules & DLL Rules:</span></span>

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a><span data-ttu-id="d6ae7-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d6ae7-121">Related topics</span></span>
<span data-ttu-id="d6ae7-122">[Présentation d’AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Référence technique AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="d6ae7-122">[What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>
