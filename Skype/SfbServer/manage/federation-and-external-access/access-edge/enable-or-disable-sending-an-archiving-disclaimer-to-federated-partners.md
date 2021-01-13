---
title: Activation ou désactivation de l’envoi d’une notification d’exclusion aux partenaires fédérés relative à l’archivage
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 1f0238e177e74dc1263208f9a6a350158825d825
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817354"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a><span data-ttu-id="60793-102">Activer ou désactiver l’envoi d’une clause d’exclusion de responsabilité d’archivage à des partenaires fédérés dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="60793-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span></span>

<span data-ttu-id="60793-p101">Lorsque vous déployez vos serveurs Edge et activez la fédération pour votre entreprise, vous devez spécifier si la notification d’exclusion relative à l’archivage doit être automatiquement envoyée aux partenaires fédérés. Si vous archivez des communications externes, vous devez activer l’envoi d’une notification d’exclusion relative à l’archivage. Utilisez la procédure de cette rubrique pour modifier cette configuration.</span><span class="sxs-lookup"><span data-stu-id="60793-p101">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners. If you archive external communications, you should enable the sending of an archiving disclaimer. Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="60793-106">La procédure suivante suppose que vous avez déjà activé la fédération pour votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="60793-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="60793-107">Pour plus d’informations sur l’activation de la fédération, voir [Activer ou désactiver l’accès des utilisateurs distants.](enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="60793-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="60793-108">Pour activer ou désactiver l’envoi d’une notification d’exclusion relative à l’archivage aux partenaires fédérés</span><span class="sxs-lookup"><span data-stu-id="60793-108">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="60793-109">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="60793-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="60793-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="60793-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="60793-111">Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Configuration du serveur Edge d’accès**.</span><span class="sxs-lookup"><span data-stu-id="60793-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="60793-112">Dans l’onglet **Configuration du serveur Edge d’accès**, cliquez sur **Global**, **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="60793-112">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="60793-113">Dans **Modifier la configuration du serveur Edge d’accès**, sous **Autoriser les communications avec des utilisateurs fédérés**, activez ou désactivez la case à cocher **Envoyer une notification d’exclusion aux partenaires fédérés relative à l’archivage** pour activer ou désactiver l’envoi automatique d’une notification d’exclusion relative à l’archivage.</span><span class="sxs-lookup"><span data-stu-id="60793-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="60793-114">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="60793-114">Click **Commit**.</span></span>

<span data-ttu-id="60793-115">Pour permettre aux utilisateurs fédérés de collaborer avec des utilisateurs dans votre déploiement Skype Entreprise Server, vous devez également avoir configuré au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="60793-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="60793-116">Pour plus d’informations sur le contrôle de l’accès pour des domaines fédérés spécifiques, voir Configurer la prise en charge des [domaines externes autorisés.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="60793-116">For details about controlling access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="60793-117">Activation ou désactivation de la clause d’exclusion de responsabilité d’archivage à l’aide Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="60793-117">Enabling or disabling the archiving disclaimer by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="60793-118">L’utilisation de la clause d’exclusion de responsabilité d’archivage peut être gérée à l’Windows PowerShell et à l'Set-CsAccessEdgeConfiguration cmdlet.</span><span class="sxs-lookup"><span data-stu-id="60793-118">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="60793-119">Cette cmdlet peut être exécuté à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60793-119">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="60793-120">Pour activer la clause d’exclusion de responsabilité d’archivage</span><span class="sxs-lookup"><span data-stu-id="60793-120">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="60793-121">Pour activer la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur True ($True) :</span><span class="sxs-lookup"><span data-stu-id="60793-121">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="60793-122">Pour désactiver la clause d’exclusion de responsabilité d’archivage</span><span class="sxs-lookup"><span data-stu-id="60793-122">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="60793-123">Pour désactiver la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur False ($False) :</span><span class="sxs-lookup"><span data-stu-id="60793-123">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


