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
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Au moment où vous avez déployé vos serveurs de périphérie et la Fédération activée pour votre organisation, vous devez indiquer si vous souhaitez prendre en charge la découverte automatique des domaines partenaires fédérés.
ms.openlocfilehash: a5569639cf870d2a5da16ef81aa733724a6701b3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280256"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="5f13f-103">Activer ou désactiver la découverte de partenaires de Fédération dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5f13f-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="5f13f-104">Au moment où vous avez déployé vos serveurs de périphérie et la Fédération activée pour votre organisation, vous devez indiquer si vous souhaitez prendre en charge la découverte automatique des domaines partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="5f13f-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="5f13f-105">Suivez la procédure décrite dans cette rubrique pour modifier cette configuration.</span><span class="sxs-lookup"><span data-stu-id="5f13f-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="5f13f-106">La procédure suivante suppose que vous avez déjà activé la Fédération pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5f13f-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="5f13f-107">Pour plus d’informations sur l’activation de la Fédération, voir [activation ou désactivation de l’accès des utilisateurs](enable-or-disable-remote-user-access.md)distants.</span><span class="sxs-lookup"><span data-stu-id="5f13f-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="5f13f-108">Pour activer ou désactiver la découverte automatique des domaines fédérés pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="5f13f-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="5f13f-109">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="5f13f-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5f13f-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="5f13f-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="5f13f-111">Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis sur **configuration de Microsoft Edge Access**.</span><span class="sxs-lookup"><span data-stu-id="5f13f-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="5f13f-112">Dans la page **configuration de Microsoft Edge** , cliquez sur **Global**, sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="5f13f-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="5f13f-113">Dans **modification**de la configuration d’un point d’accès, sous **activer les communications avec des utilisateurs fédérés**, activez ou désactivez la case à cocher **activer la découverte** automatique du domaine pour activer ou désactiver la découverte automatique des domaines partenaires.</span><span class="sxs-lookup"><span data-stu-id="5f13f-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="5f13f-114">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="5f13f-114">Click **Commit**.</span></span>

<span data-ttu-id="5f13f-115">Pour permettre aux utilisateurs fédérés de collaborer avec des utilisateurs dans le déploiement de Skype entreprise Server, vous devez également avoir configuré au moins une stratégie d’accès externe pour la prise en charge de l’accès des utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="5f13f-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="5f13f-116">Pour plus d’informations, voir [activer ou désactiver la connectivité de Fédération et de messagerie instantanée publique](enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="5f13f-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="5f13f-117">Pour plus d’informations sur le contrôle de l’accès pour des domaines fédérés spécifiques, voir [gérer les domaines fédérés SIP](../sip-domains/manage-sip-federated-domains-for-your-organization.md) et gérer les [fournisseurs fédérés SIP](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="5f13f-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5f13f-118">Activation ou désactivation de la découverte de partenaires de Fédération à l’aide d’applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f13f-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="5f13f-119">La découverte des partenaires de Fédération peut être gérée à l’aide de Windows PowerShell et de l’applet de la cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="5f13f-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="5f13f-120">Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f13f-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="5f13f-121">Pour activer la découverte des partenaires de Fédération</span><span class="sxs-lookup"><span data-stu-id="5f13f-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="5f13f-122">Pour activer la découverte des partenaires de Fédération, définissez la valeur de la propriété **EnablePartnerDiscovery** sur True ($true).</span><span class="sxs-lookup"><span data-stu-id="5f13f-122">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="5f13f-123">Notez que vous devez activer le routage DNS SRV pour pouvoir modifier cette valeur de propriété.</span><span class="sxs-lookup"><span data-stu-id="5f13f-123">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="5f13f-124">Pour désactiver la découverte des partenaires de Fédération</span><span class="sxs-lookup"><span data-stu-id="5f13f-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="5f13f-125">Pour désactiver la découverte des partenaires de Fédération, définissez la valeur de la propriété **EnablePartnerDiscovery** sur false ($false):</span><span class="sxs-lookup"><span data-stu-id="5f13f-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

