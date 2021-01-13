---
title: Configurer des clauses d’exclusion de responsabilité d’archivage pour les utilisateurs externes dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Résumé : Lisez cette rubrique pour découvrir comment configurer une clause d’exclusion de responsabilité d’archivage pour Skype Entreprise Server.'
ms.openlocfilehash: 055c94f0fba18dcd9de35ff5a73e37de0b45595b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820664"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a><span data-ttu-id="abea3-103">Configurer des clauses d’exclusion de responsabilité d’archivage pour les utilisateurs externes dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="abea3-103">Configure archiving disclaimers for external users in Skype for Business Server</span></span>
 
<span data-ttu-id="abea3-104">**Résumé :** Lisez cette rubrique pour découvrir comment configurer une clause d’exclusion de responsabilité d’archivage pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="abea3-104">**Summary:** Read this topic to learn how to configure an archiving disclaimer for Skype for Business Server.</span></span>
  
<span data-ttu-id="abea3-105">Si votre organisation communique avec des partenaires externes, vous devez leur faire savoir que vous archivez les communications avec eux.</span><span class="sxs-lookup"><span data-stu-id="abea3-105">If your organization communicates with external partners, you need to let them know that you are archiving communications with them.</span></span> <span data-ttu-id="abea3-106">Lorsque vous déployez un serveur Edge et activez la fédération pour votre organisation, vous êtes invité à envoyer automatiquement une clause d’exclusion de responsabilité d’archivage à des partenaires externes.</span><span class="sxs-lookup"><span data-stu-id="abea3-106">When you deploy an Edge Server and enable federation for your organization, you are asked whether you want to automatically send an archiving disclaimer to external partners.</span></span> 
  
<span data-ttu-id="abea3-107">Si vous devez modifier cette configuration, vous pouvez utiliser le Panneau de configuration Skype Entreprise Server ou l’Windows PowerShell **Set-CsAccessEdgeConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="abea3-107">If you need to change this configuration, you can use the Skype for Business Server Control Panel or the Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="abea3-108">Les cmdlets peuvent être exécutés à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="abea3-108">Cmdlets can be run either from the Skype for Business Server management shell or from a remote session of Windows PowerShell.</span></span>
  
<span data-ttu-id="abea3-109">Pour permettre aux utilisateurs externes de collaborer avec des utilisateurs dans votre déploiement Skype Entreprise Server, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="abea3-109">To enable external users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support external user access.</span></span> <span data-ttu-id="abea3-110">Pour plus d’informations, voir Manage XMPP Federated Partners for Your Organization.</span><span class="sxs-lookup"><span data-stu-id="abea3-110">For details, see Manage XMPP Federated Partners for Your Organization.</span></span> <span data-ttu-id="abea3-111">Pour plus d’informations sur le contrôle de l’accès pour des domaines fédérés spécifiques, voir Control Access by Individual Federated Domains.</span><span class="sxs-lookup"><span data-stu-id="abea3-111">For details about controlling access for specific federated domains, see Control Access by Individual Federated Domains.</span></span>
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a><span data-ttu-id="abea3-112">Activer ou désactiver la clause d’exclusion de responsabilité d’archivage à l’aide du Panneau de contrôle</span><span class="sxs-lookup"><span data-stu-id="abea3-112">Enable or disable archiving disclaimer using the Control Panel</span></span>

1. <span data-ttu-id="abea3-113">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="abea3-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="abea3-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="abea3-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="abea3-115">Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Configuration du serveur Edge d’accès**.</span><span class="sxs-lookup"><span data-stu-id="abea3-115">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>
    
4. <span data-ttu-id="abea3-116">Dans l’onglet **Configuration du serveur Edge d’accès**, cliquez sur **Global**, **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="abea3-116">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="abea3-117">Dans Modifier la **configuration** du edge d’accès, sous  Activer la fédération et la connectivité **DE** messagerie instantanée publique, activez ou désactivez la case à cocher Envoyer la clause d’exclusion de responsabilité d’archivage aux partenaires fédérés pour activer ou désactiver l’envoi automatique de la clause d’exclusion de responsabilité d’archivage.</span><span class="sxs-lookup"><span data-stu-id="abea3-117">In **Edit Access Edge Configuration**, under **Enable federation and public IM connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>
    
6. <span data-ttu-id="abea3-118">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="abea3-118">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a><span data-ttu-id="abea3-119">Activer ou désactiver la clause d’exclusion de responsabilité d’archivage à l’aide Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="abea3-119">Enable or disable archiving disclaimer using Windows PowerShell</span></span>

<span data-ttu-id="abea3-120">Pour activer la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur True ($True) :</span><span class="sxs-lookup"><span data-stu-id="abea3-120">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

<span data-ttu-id="abea3-121">Pour désactiver la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur False ($False) :</span><span class="sxs-lookup"><span data-stu-id="abea3-121">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


