---
title: Configurer l’intégration avec le stockage Exchange pour Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Résumé : Lisez cette rubrique pour savoir comment configurer l’intégration avec le stockage Exchange dans Skype pour Business Server.'
ms.openlocfilehash: 4b9d689ef5315c58b2fb6d78c01366ce2377a00e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893545"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a><span data-ttu-id="ab07b-103">Configurer l’intégration avec le stockage Exchange pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="ab07b-103">Configure integration with Exchange storage for Skype for Business Server</span></span>
 
<span data-ttu-id="ab07b-104">**Résumé :** Lisez cette rubrique pour savoir comment configurer l’intégration avec le stockage Exchange dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="ab07b-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server.</span></span>
  
<span data-ttu-id="ab07b-105">Si vous utilisez l’intégration de Microsoft Exchange pour tous les utilisateurs dans votre déploiement, vous n’avez pas besoin de configurer Skype pour les stratégies d’archivage Business Server pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ab07b-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="ab07b-106">Au lieu de cela, vous configurez des stratégies de blocage sur Place Exchange pour prendre en charge l’archivage pour les utilisateurs hébergés sur Exchange, avec leurs boîtes aux lettres mettre en blocage sur Place.</span><span class="sxs-lookup"><span data-stu-id="ab07b-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="ab07b-107">Avant de configurer l’intégration avec le stockage Exchange, lisez [Plan pour l’archivage dans Skype pour Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="ab07b-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="ab07b-108">Pour plus d’informations sur les stratégies de blocage sur Place Exchange, voir la documentation du produit Exchange.</span><span class="sxs-lookup"><span data-stu-id="ab07b-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="ab07b-109">Configurer l’intégration avec le stockage de Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="ab07b-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="ab07b-110">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ab07b-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ab07b-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="ab07b-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="ab07b-112">Dans la barre de navigation de gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **Configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="ab07b-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="ab07b-113">Cliquez sur le nom de la configuration de site, de pool ou globale appropriée dans la liste des configurations d’archivage, puis sur **Modifier**, sur **Afficher les détails** et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ab07b-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="ab07b-114">Pour activer l’intégration avec le stockage Exchange, activez la case à cocher **intégration de Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="ab07b-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="ab07b-115">Pour désactiver l’intégration avec le stockage Exchange, désactivez la case à cocher **intégration de Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="ab07b-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="ab07b-116">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="ab07b-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="ab07b-117">Lorsque Skype pour Business Server et Microsoft Exchange sont déployés dans des forêts différentes</span><span class="sxs-lookup"><span data-stu-id="ab07b-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="ab07b-118">Si vous utilisez l’intégration de Microsoft Exchange et Microsoft Exchange Server n’est pas déployé dans la même forêt que Skype pour Business Server, vous devez vous assurer que les attributs Active Directory d’Exchange suivants sont synchronisés avec la forêt où Skype pour Business Server est déployé :</span><span class="sxs-lookup"><span data-stu-id="ab07b-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="ab07b-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="ab07b-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="ab07b-120">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="ab07b-120">proxyAddresses</span></span>
    
<span data-ttu-id="ab07b-p102">Cet attribut gère plusieurs valeurs. Lorsque vous synchronisez cet attribut, vous devez fusionner les valeurs, et non les remplacer afin de veiller à ce que les valeurs existantes ne soient pas perdues.</span><span class="sxs-lookup"><span data-stu-id="ab07b-p102">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

