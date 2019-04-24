---
title: Configurer des notifications d’exclusion d’archivage pour les utilisateurs externes Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Résumé : Lisez cette rubrique pour savoir comment configurer une notification d’exclusion d’archivage pour Skype pour Business Server.'
ms.openlocfilehash: 9511dacb23773a4cd411844abd1d38216026019e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32227558"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a><span data-ttu-id="4af94-103">Configurer des notifications d’exclusion d’archivage pour les utilisateurs externes Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="4af94-103">Configure archiving disclaimers for external users in Skype for Business Server</span></span>
 
<span data-ttu-id="4af94-104">**Résumé :** Lisez cette rubrique pour savoir comment configurer une notification d’exclusion d’archivage pour Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="4af94-104">**Summary:** Read this topic to learn how to configure an archiving disclaimer for Skype for Business Server.</span></span>
  
<span data-ttu-id="4af94-105">Si votre organisation communique avec des partenaires externes, vous devez leur faire savoir que vous archivez vos communications.</span><span class="sxs-lookup"><span data-stu-id="4af94-105">If your organization communicates with external partners, you need to let them know that you are archiving communications with them.</span></span> <span data-ttu-id="4af94-106">Lorsque vous déployez un serveur de périphérie et activez la fédération pour votre organisation, vous êtes invité si vous souhaitez envoyer automatiquement une notification d’exclusion d’archivage aux partenaires externes.</span><span class="sxs-lookup"><span data-stu-id="4af94-106">When you deploy an Edge Server and enable federation for your organization, you are asked whether you want to automatically send an archiving disclaimer to external partners.</span></span> 
  
<span data-ttu-id="4af94-107">Si vous devez modifier cette configuration, vous pouvez utiliser la Skype pour le panneau de configuration serveur Business ou l’applet de commande Windows PowerShell **Set-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="4af94-107">If you need to change this configuration, you can use the Skype for Business Server Control Panel or the Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="4af94-108">Applets de commande peut être exécutée à partir de la Skype pour le shell de gestion Business Server ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4af94-108">Cmdlets can be run either from the Skype for Business Server management shell or from a remote session of Windows PowerShell.</span></span>
  
<span data-ttu-id="4af94-109">Pour permettre aux utilisateurs externes de collaborer avec des utilisateurs dans votre Skype pour le déploiement de serveur d’entreprise, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="4af94-109">To enable external users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support external user access.</span></span> <span data-ttu-id="4af94-110">Pour plus d’informations, voir Manage XMPP Federated Partners for Your Organization.</span><span class="sxs-lookup"><span data-stu-id="4af94-110">For details, see Manage XMPP Federated Partners for Your Organization.</span></span> <span data-ttu-id="4af94-111">Pour plus d’informations sur le contrôle d’accès de domaines fédérés spécifiques, reportez-vous à Control Access by Individual Federated Domains.</span><span class="sxs-lookup"><span data-stu-id="4af94-111">For details about controlling access for specific federated domains, see Control Access by Individual Federated Domains.</span></span>
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a><span data-ttu-id="4af94-112">Activer ou désactiver une nouvelle notification d’exclusion relative à l’archivage à l’aide du panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="4af94-112">Enable or disable archiving disclaimer using the Control Panel</span></span>

1. <span data-ttu-id="4af94-113">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="4af94-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4af94-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="4af94-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="4af94-115">Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Configuration du serveur Edge d’accès**.</span><span class="sxs-lookup"><span data-stu-id="4af94-115">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>
    
4. <span data-ttu-id="4af94-116">Sous l’onglet **Configuration du serveur Edge d’accès**, cliquez sur **Global**, **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="4af94-116">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="4af94-117">Dans **Modifier la configuration du serveur Edge d’accès**, sous **Activer la fédération et la connectivité PIC**, activez ou désactivez la case à cocher **Envoyer une notification d’exclusion aux partenaires fédérés relative à l’archivage** pour activer ou désactiver l’envoi automatique d’une notification d’exclusion relative à l’archivage.</span><span class="sxs-lookup"><span data-stu-id="4af94-117">In **Edit Access Edge Configuration**, under **Enable federation and public IM connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>
    
6. <span data-ttu-id="4af94-118">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="4af94-118">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a><span data-ttu-id="4af94-119">Activer ou désactiver une nouvelle notification d’exclusion relative à l’archivage à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4af94-119">Enable or disable archiving disclaimer using Windows PowerShell</span></span>

<span data-ttu-id="4af94-120">Pour activer la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur True ($True) :</span><span class="sxs-lookup"><span data-stu-id="4af94-120">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

<span data-ttu-id="4af94-121">Pour désactiver la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur False ($False) :</span><span class="sxs-lookup"><span data-stu-id="4af94-121">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


