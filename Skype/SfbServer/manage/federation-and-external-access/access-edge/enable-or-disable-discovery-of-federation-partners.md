---
title: Activation ou désactivation de la découverte de partenaires de fédération
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
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
description: Lorsque vous déployez vos serveurs Edge et activez la fédération pour votre entreprise, vous devez spécifier si la découverte des domaines partenaires fédérés doit être prise en charge automatiquement.
ms.openlocfilehash: e1f076b725dff149f024a3fd59f9f7d52da4e6a8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817424"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="1dcd3-103">Activer ou désactiver la découverte de partenaires de fédération dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1dcd3-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="1dcd3-p101">Lorsque vous déployez vos serveurs Edge et activez la fédération pour votre entreprise, vous devez spécifier si la découverte des domaines partenaires fédérés doit être prise en charge automatiquement. Utilisez la procédure de cette rubrique pour modifier cette configuration.</span><span class="sxs-lookup"><span data-stu-id="1dcd3-p101">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains. Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="1dcd3-106">La procédure suivante suppose que vous avez déjà activé la fédération pour votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="1dcd3-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="1dcd3-107">Pour plus d’informations sur l’activation de la fédération, voir [Activer ou désactiver l’accès des utilisateurs distants.](enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="1dcd3-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="1dcd3-108">Pour activer ou désactiver la découverte automatique des domaines fédérés pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="1dcd3-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="1dcd3-109">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1dcd3-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1dcd3-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1dcd3-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="1dcd3-111">Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Configuration du serveur Edge d’accès**.</span><span class="sxs-lookup"><span data-stu-id="1dcd3-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="1dcd3-112">Dans la page **Configuration du serveur Edge d’accès**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1dcd3-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1dcd3-113">Dans **Modifier la configuration du serveur Edge d’accès**, sous **Autoriser les communications avec des utilisateurs fédérés**, activez ou désactivez la case à cocher **Activer la découverte du domaine partenaire** pour activer ou désactiver la découverte automatique des domaines partenaires.</span><span class="sxs-lookup"><span data-stu-id="1dcd3-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="1dcd3-114">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1dcd3-114">Click **Commit**.</span></span>

<span data-ttu-id="1dcd3-115">Pour permettre aux utilisateurs fédérés de collaborer avec des utilisateurs dans votre déploiement Skype Entreprise Server, vous devez également avoir configuré au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="1dcd3-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="1dcd3-116">Pour plus d’informations, [voir Activer ou désactiver la fédération et la connectivité DE messagerie instantanée publique.](enable-or-disable-federation-and-public-im-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="1dcd3-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="1dcd3-117">Pour plus d’informations sur le contrôle de l’accès pour des domaines fédérés spécifiques, voir Gérer les domaines fédérés [SIP](../sip-domains/manage-sip-federated-domains-for-your-organization.md) et Gérer les fournisseurs fédérés [SIP.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="1dcd3-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1dcd3-118">Activation ou désactivation de la découverte de partenaires de fédération à l’aide Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="1dcd3-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="1dcd3-119">La découverte des partenaires de fédération peut être gérée à l’Windows PowerShell l'Set-CsAccessEdgeConfiguration cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1dcd3-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="1dcd3-120">Cette cmdlet peut être exécuté à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1dcd3-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="1dcd3-121">Pour activer la découverte des partenaires de fédération</span><span class="sxs-lookup"><span data-stu-id="1dcd3-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="1dcd3-p105">Pour activer la découverte des partenaires de fédération, définissez la valeur de la propriété **EnablePartnerDiscovery** à True ($True). Notez que vous devez activer le routage DNS SRV afin de changer la valeur de cette propriété.</span><span class="sxs-lookup"><span data-stu-id="1dcd3-p105">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True). Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="1dcd3-124">Pour désactiver la découverte des partenaires de fédération</span><span class="sxs-lookup"><span data-stu-id="1dcd3-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="1dcd3-125">Pour désactiver la découverte des partenaires de fédération, définissez la valeur de la propriété **EnablePartnerDiscovery** à False ($False).</span><span class="sxs-lookup"><span data-stu-id="1dcd3-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

