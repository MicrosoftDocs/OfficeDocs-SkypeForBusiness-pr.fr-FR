---
title: Activation ou désactivation de l’envoi d’une notification d’exclusion relative à l’archivage aux partenaires fédérés
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: c2f64a617cae938ffe64ec8db313402785413c49
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280214"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a><span data-ttu-id="da9e9-102">Activation ou désactivation de l’envoi d’une exclusion d’archivage aux partenaires fédérés dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="da9e9-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span></span>

<span data-ttu-id="da9e9-103">Lors du déploiement de vos serveurs de périphérie et de la Fédération activée pour votre organisation, vous devez indiquer si vous souhaitez envoyer automatiquement l’exclusion de responsabilité aux partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="da9e9-103">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="da9e9-104">Si vous archivez des communications externes, vous devez autoriser l’envoi d’une exclusion de responsabilité d’archivage.</span><span class="sxs-lookup"><span data-stu-id="da9e9-104">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="da9e9-105">Suivez la procédure décrite dans cette rubrique pour modifier cette configuration.</span><span class="sxs-lookup"><span data-stu-id="da9e9-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="da9e9-106">La procédure suivante suppose que vous avez déjà activé la Fédération pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="da9e9-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="da9e9-107">Pour plus d’informations sur l’activation de la Fédération, voir [activation ou désactivation de l’accès des utilisateurs](enable-or-disable-remote-user-access.md)distants.</span><span class="sxs-lookup"><span data-stu-id="da9e9-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="da9e9-108">Pour activer ou désactiver l’envoi d’une exclusion d’autorisation d’archivage aux partenaires fédérés</span><span class="sxs-lookup"><span data-stu-id="da9e9-108">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="da9e9-109">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="da9e9-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="da9e9-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="da9e9-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="da9e9-111">Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis sur **configuration de Microsoft Edge Access**.</span><span class="sxs-lookup"><span data-stu-id="da9e9-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="da9e9-112">Sous l’onglet **Configuration du serveur Edge d’accès**, cliquez sur **Global**, **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="da9e9-112">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="da9e9-113">Dans **modification de la configuration d’Access Edge**, sous **activer les communications avec des utilisateurs fédérés**, activez ou désactivez la case à cocher **Envoyer un courrier électronique d’envoi aux partenaires fédérés** pour activer ou désactiver l’envoi automatique de l’archivage relative.</span><span class="sxs-lookup"><span data-stu-id="da9e9-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="da9e9-114">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="da9e9-114">Click **Commit**.</span></span>

<span data-ttu-id="da9e9-115">Pour permettre aux utilisateurs fédérés de collaborer avec des utilisateurs dans le déploiement de Skype entreprise Server, vous devez également avoir configuré au moins une stratégie d’accès externe pour la prise en charge de l’accès des utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="da9e9-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="da9e9-116">Pour plus d’informations sur le contrôle de l’accès pour des domaines fédérés spécifiques, voir [configurer la prise en charge des domaines externes autorisés](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="da9e9-116">For details about controlling access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="da9e9-117">Activation ou désactivation de l’exclusion de responsabilité de l’archivage à l’aide d’applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="da9e9-117">Enabling or disabling the archiving disclaimer by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="da9e9-118">L’utilisation de la clause d’exclusion de responsabilité d’archivage peut être gérée à l’aide de Windows PowerShell et de l’applet de passe Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="da9e9-118">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="da9e9-119">Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da9e9-119">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="da9e9-120">Pour activer le démenti d’archivage</span><span class="sxs-lookup"><span data-stu-id="da9e9-120">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="da9e9-121">Pour activer la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur True ($True) :</span><span class="sxs-lookup"><span data-stu-id="da9e9-121">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="da9e9-122">Pour désactiver la clause d’exclusion de responsabilité d’archivage</span><span class="sxs-lookup"><span data-stu-id="da9e9-122">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="da9e9-123">Pour désactiver la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur False ($False) :</span><span class="sxs-lookup"><span data-stu-id="da9e9-123">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


