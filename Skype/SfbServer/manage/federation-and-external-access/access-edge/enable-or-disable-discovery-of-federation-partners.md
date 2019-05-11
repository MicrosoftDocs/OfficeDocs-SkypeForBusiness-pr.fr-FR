---
title: Activation ou désactivation de la découverte de partenaires de fédération
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Au moment où vous déployé vos serveurs de périphérie et activé la fédération pour votre organisation, doit avoir spécifié s’il faut prendre en charge la découverte automatique des domaines de partenaire fédéré.
ms.openlocfilehash: cf12190b03df30f4a15f6ed5e0499aa97c66e576
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919513"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="1adcd-103">Activer ou désactiver la découverte des partenaires de fédération dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="1adcd-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="1adcd-104">Au moment où vous déployé vos serveurs de périphérie et activé la fédération pour votre organisation, doit avoir spécifié s’il faut prendre en charge la découverte automatique des domaines de partenaire fédéré.</span><span class="sxs-lookup"><span data-stu-id="1adcd-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="1adcd-105">Utilisez la procédure de cette rubrique pour modifier cette configuration.</span><span class="sxs-lookup"><span data-stu-id="1adcd-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="1adcd-106">La procédure suivante suppose que vous avez déjà activé la fédération pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1adcd-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="1adcd-107">Pour plus d’informations sur l’activation de la fédération, voir [Activer ou désactiver l’accès des utilisateurs distants](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="1adcd-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="1adcd-108">Pour activer ou désactiver la découverte automatique des domaines fédérés pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="1adcd-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="1adcd-109">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1adcd-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1adcd-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="1adcd-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="1adcd-111">Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, cliquez sur **Configuration du serveur Edge d’accès**.</span><span class="sxs-lookup"><span data-stu-id="1adcd-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="1adcd-112">Dans la page **Configuration du serveur Edge d’accès** , cliquez sur **Global**, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1adcd-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1adcd-113">Dans **Modifier la Configuration Edge accès**, sous **Activer les communications avec les utilisateurs fédérés**, activez ou désactivez la case à cocher **Activer la découverte du domaine partenaire** pour activer ou désactiver la découverte automatique des domaines partenaires.</span><span class="sxs-lookup"><span data-stu-id="1adcd-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="1adcd-114">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1adcd-114">Click **Commit**.</span></span>

<span data-ttu-id="1adcd-115">Pour permettre aux utilisateurs fédérés de collaborer avec des utilisateurs dans votre Skype pour le déploiement de serveur d’entreprise, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="1adcd-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="1adcd-116">Pour plus d’informations, voir [Activer ou désactiver la fédération et la connectivité PIC](enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="1adcd-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="1adcd-117">Pour plus d’informations sur le contrôle d’accès pour des domaines fédérés spécifiques, voir [Gérer SIP des domaines fédérés](../sip-domains/manage-sip-federated-domains-for-your-organization.md) et [Gérer SIP fournisseurs fédérés](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="1adcd-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1adcd-118">Activation ou désactivation de la détection des partenaires de fédération à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1adcd-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="1adcd-119">Découverte des partenaires de fédération peut être gérée à l’aide de Windows PowerShell et l’applet de commande Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="1adcd-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="1adcd-120">Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1adcd-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="1adcd-121">Pour activer la découverte des partenaires de fédération</span><span class="sxs-lookup"><span data-stu-id="1adcd-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="1adcd-122">Pour activer la découverte des partenaires de fédération, définissez la valeur de la propriété **EnablePartnerDiscovery** sur True ($True).</span><span class="sxs-lookup"><span data-stu-id="1adcd-122">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="1adcd-123">Notez que vous devez activer DNS SRV routage afin de modifier la valeur de cette propriété.</span><span class="sxs-lookup"><span data-stu-id="1adcd-123">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="1adcd-124">Pour désactiver la découverte des partenaires de fédération</span><span class="sxs-lookup"><span data-stu-id="1adcd-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="1adcd-125">Pour désactiver la découverte des partenaires de fédération, définissez la valeur de la propriété **EnablePartnerDiscovery** à False ($False) :</span><span class="sxs-lookup"><span data-stu-id="1adcd-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

