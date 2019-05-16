---
title: Stratégies de contrôle d’application AppLocker dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
description: Découvrez comment activer le client de bureau équipes avec les stratégies de contrôle d’application AppLocker.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04379cad0ab224915a02475b010f908d486284cc
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34063208"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="9a3f2-103">Stratégies de contrôle d’application AppLocker dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9a3f2-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="9a3f2-104">Cet article explique comment activer l’application de client de bureau équipes avec les stratégies de contrôle d’application AppLocker.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="9a3f2-105">Utilisation de AppLocker est conçue pour restreindre l’exécution du programme et script par les utilisateurs non administratifs.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="9a3f2-106">Pour plus d’informations et pour obtenir des instructions sur AppLocker, consultez la rubrique [What ' s AppLocker ?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span><span class="sxs-lookup"><span data-stu-id="9a3f2-106">For more information and guidance on AppLocker, see [What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="9a3f2-107">Le processus d’activation des équipes avec AppLocker requiert la création de stratégies de création de listes autorisées basée sur AppLocker.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based whitelisting policies.</span></span> <span data-ttu-id="9a3f2-108">Les stratégies sont créées avec l’utilisation des applets de commande Windows PowerShell pour AppLocker et/ou le logiciel de gestion de stratégie de groupe (voir la [référence technique AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) pour plus d’informations).</span><span class="sxs-lookup"><span data-stu-id="9a3f2-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="9a3f2-109">La stratégie AppLocker est enregistrée au format XML et peut être modifiée avec n’importe quel texte ou un éditeur XML.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-whitelisting-with-applocker"></a><span data-ttu-id="9a3f2-110">Création de listes autorisées équipes avec AppLocker</span><span class="sxs-lookup"><span data-stu-id="9a3f2-110">Teams whitelisting with AppLocker</span></span>

<span data-ttu-id="9a3f2-111">Règles AppLocker sont organisés en ensembles de règles.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="9a3f2-112">Appliquent des règles AppLocker à l’application cible, et elles sont les composants qui constituent la stratégie AppLocker.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="9a3f2-113">Aux équipes d’autorisation, nous vous recommandons d’utiliser les [règles de condition publisher](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) étant donné que tous les fichiers d’application équipes sont signés numériquement.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-113">To whitelist Teams, we recommend that you use the [publisher condition rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="9a3f2-114">L’utilisation de règles de chemin d’accès est déconseillée, car le répertoire d’installation équipes est accessible en écriture pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="9a3f2-115">Également n’est pas recommandé l’utilisation de règles de hachage, car les règles devra être mis à jour chaque fois que l’application cliente les équipes est mis à jour.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="9a3f2-116">Dans la mesure où les fichiers exécutables du bureau équipes sont signés numériquement, la condition éditeur identifie un fichier d’application en fonction de sa signature numérique et les attributs de version incorporées.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="9a3f2-117">La signature numérique contient des informations sur la société qui a créé le fichier d’application (l’éditeur).</span><span class="sxs-lookup"><span data-stu-id="9a3f2-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="9a3f2-118">Les informations de version, qui sont obtenues à partir de la ressource binaire, incluent le nom du produit faisant partie de fichier et le numéro de version du fichier d’application.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="9a3f2-119">Exemple de règles de condition publisher</span><span class="sxs-lookup"><span data-stu-id="9a3f2-119">Example of publisher condition rules</span></span>

<span data-ttu-id="9a3f2-120">Pour l’application cliente équipes (tous les fichiers, toutes les versions) :</span><span class="sxs-lookup"><span data-stu-id="9a3f2-120">For the Teams client app (all files, all versions):</span></span>

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
```

## <a name="related-topics"></a><span data-ttu-id="9a3f2-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9a3f2-121">Related topics</span></span>
<span data-ttu-id="9a3f2-122">[What ' s AppLocker ?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [AppLocker Guide de référence technique](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="9a3f2-122">[What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>