---
title: Activation ou désactivation de l’envoi d’une notification d’exclusion relative à l’archivage aux partenaires fédérés
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 3e076e1044a65c45a8fc72d0e7d54369d4c3196f
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222778"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a><span data-ttu-id="2d531-102">Activer ou désactiver l’envoi d’une notification d’exclusion d’archivage aux partenaires fédérés dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="2d531-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span></span>

<span data-ttu-id="2d531-103">Au moment où vous déployé vos serveurs de périphérie et activé la fédération pour votre organisation, doit avoir spécifié s’il faut automatiquement envoyer la notification d’exclusion d’archivage aux partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="2d531-103">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="2d531-104">Si vous archivez les communications externes, vous devez activer l’envoi d’une notification d’exclusion d’archivage.</span><span class="sxs-lookup"><span data-stu-id="2d531-104">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="2d531-105">Utilisez la procédure de cette rubrique pour modifier cette configuration.</span><span class="sxs-lookup"><span data-stu-id="2d531-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="2d531-106">La procédure suivante suppose que vous avez déjà activé la fédération pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2d531-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="2d531-107">Pour plus d’informations sur l’activation de la fédération, voir [Activer ou désactiver l’accès des utilisateurs distants](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="2d531-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="2d531-108">Pour activer ou désactiver l’envoi d’une notification d’exclusion d’archivage aux partenaires fédérés</span><span class="sxs-lookup"><span data-stu-id="2d531-108">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="2d531-109">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="2d531-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2d531-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="2d531-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2d531-111">Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, cliquez sur **Configuration du serveur Edge d’accès**.</span><span class="sxs-lookup"><span data-stu-id="2d531-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="2d531-112">Sous l’onglet **Configuration du serveur Edge d’accès**, cliquez sur **Global**, **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="2d531-112">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2d531-113">Dans **Modifier la Configuration Edge accès**, sous **Activer les communications avec les utilisateurs fédérés**, activez ou désactivez la case à cocher **Envoyer l’archivage de notification d’exclusion aux partenaires fédérés** pour activer ou désactiver l’envoi de l’archivage automatique notification d’exclusion.</span><span class="sxs-lookup"><span data-stu-id="2d531-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="2d531-114">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="2d531-114">Click **Commit**.</span></span>

<span data-ttu-id="2d531-115">Pour permettre aux utilisateurs fédérés de collaborer avec des utilisateurs dans votre Skype pour le déploiement de serveur d’entreprise, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="2d531-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="2d531-116">Pour plus d’informations sur le contrôle d’accès pour des domaines fédérés spécifiques, voir [Configure prise en charge pour les domaines externes autorisés](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="2d531-116">For details about controlling access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2d531-117">Activation ou désactivation de la notification d’exclusion d’archivage à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d531-117">Enabling or disabling the archiving disclaimer by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="2d531-118">L’utilisation de la notification d’exclusion d’archivage peut être gérée à l’aide de Windows PowerShell et l’applet de commande Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="2d531-118">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="2d531-119">Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d531-119">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="2d531-120">Pour activer la notification d’exclusion d’archivage</span><span class="sxs-lookup"><span data-stu-id="2d531-120">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="2d531-121">Pour activer la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur True ($True) :</span><span class="sxs-lookup"><span data-stu-id="2d531-121">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="2d531-122">Pour désactiver la notification d’exclusion d’archivage</span><span class="sxs-lookup"><span data-stu-id="2d531-122">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="2d531-123">Pour désactiver la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur False ($False) :</span><span class="sxs-lookup"><span data-stu-id="2d531-123">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


