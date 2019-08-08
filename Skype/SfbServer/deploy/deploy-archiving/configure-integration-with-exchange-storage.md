---
title: Configurer l’intégration avec le stockage Exchange pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Résumé: cette rubrique vous explique comment configurer l’intégration avec le stockage Exchange dans Skype entreprise Server.'
ms.openlocfilehash: 72caf77c81dae538f793afe6f0a94ad6b61d0fa5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234330"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a><span data-ttu-id="a6eb7-103">Configurer l’intégration avec le stockage Exchange pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a6eb7-103">Configure integration with Exchange storage for Skype for Business Server</span></span>
 
<span data-ttu-id="a6eb7-104">**Résumé:** Pour plus d’informations sur la configuration de l’intégration avec le stockage Exchange dans Skype entreprise Server, reportez-vous à cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="a6eb7-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server.</span></span>
  
<span data-ttu-id="a6eb7-105">Si vous utilisez l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous n’avez pas besoin de configurer les stratégies d’archivage de Skype entreprise Server pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a6eb7-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="a6eb7-106">Au lieu de cela, vous configurez les stratégies de conservation inaltérable pour la prise en charge de l’archivage pour les utilisateurs hébergés sur Exchange, et leurs boîtes aux lettres sont placées dans la conservation inaltérable.</span><span class="sxs-lookup"><span data-stu-id="a6eb7-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="a6eb7-107">Avant de configurer l’intégration avec le stockage Exchange, voir [plan d’archivage dans Skype entreprise Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="a6eb7-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="a6eb7-108">Pour plus d’informations sur les stratégies de conservation inaltérable d’Exchange, voir la documentation du produit Exchange.</span><span class="sxs-lookup"><span data-stu-id="a6eb7-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="a6eb7-109">Configurer l’intégration avec Microsoft Exchange Storage</span><span class="sxs-lookup"><span data-stu-id="a6eb7-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="a6eb7-110">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a6eb7-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a6eb7-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a6eb7-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a6eb7-112">Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="a6eb7-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="a6eb7-113">Cliquez sur le nom de la configuration de site, de pool ou globale appropriée dans la liste des configurations d’archivage, puis sur **Modifier**, sur **Afficher les détails** et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a6eb7-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="a6eb7-114">Pour activer l’intégration à Exchange Storage, activez la case à cocher **intégration Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="a6eb7-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="a6eb7-115">Pour désactiver l’intégration à Exchange Storage, décochez la case **intégration de Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="a6eb7-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="a6eb7-116">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a6eb7-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="a6eb7-117">Lorsque Skype entreprise Server et Microsoft Exchange sont déployés dans différentes forêts</span><span class="sxs-lookup"><span data-stu-id="a6eb7-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="a6eb7-118">Si vous utilisez l’intégration de Microsoft Exchange et que Microsoft Exchange Server n’est pas déployé dans la même forêt que Skype entreprise Server, vous devez vous assurer que les attributs d’annuaire Active Directory suivants sont synchronisés avec la forêt où Skype pour Le déploiement d’Business Server est le suivant:</span><span class="sxs-lookup"><span data-stu-id="a6eb7-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="a6eb7-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="a6eb7-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="a6eb7-120">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="a6eb7-120">proxyAddresses</span></span>
    
<span data-ttu-id="a6eb7-p102">Cet attribut gère plusieurs valeurs. Lorsque vous synchronisez cet attribut, vous devez fusionner les valeurs, et non les remplacer afin de veiller à ce que les valeurs existantes ne soient pas perdues.</span><span class="sxs-lookup"><span data-stu-id="a6eb7-p102">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

