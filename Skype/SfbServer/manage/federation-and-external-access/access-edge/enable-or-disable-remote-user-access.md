---
title: Activation ou désactivation de l’accès des utilisateurs distants
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si vous activez l’accès des utilisateurs distants pour les utilisateurs distants, les utilisateurs distants pris en charge se connectent via Internet et n’ont pas besoin de se connecter à l’aide d’un VPN pour collaborer avec des utilisateurs internes utilisant Skype entreprise Server.
ms.openlocfilehash: dde2bbb2d71d84bc9102683afc37208e3c4616bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280235"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="f6c5f-103">Activation ou désactivation de l’accès des utilisateurs distants dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="f6c5f-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="f6c5f-104">Les utilisateurs distants sont les utilisateurs de votre organisation qui ont une identité Active Directory persistante au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="f6c5f-105">Les utilisateurs distants se connectent souvent à Skype entreprise Server depuis l’extérieur de votre réseau à l’aide d’un réseau privé virtuel (VPN) lorsqu’ils ne sont pas connectés au réseau de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="f6c5f-106">Les utilisateurs distants incluent des employés travaillant à la maison ou en déplacement, ainsi que d’autres travailleurs distants, tels que des fournisseurs approuvés qui ont reçu des informations d’identification d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="f6c5f-107">Si vous activez l’accès des utilisateurs distants pour les utilisateurs distants, les utilisateurs distants pris en charge se connectent via Internet et n’ont pas besoin de se connecter à l’aide d’un VPN pour collaborer avec des utilisateurs internes utilisant Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="f6c5f-108">Pour prendre en charge l’accès des utilisateurs distants, vous devez activer l’accès des utilisateurs distants.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="f6c5f-109">Lorsque vous activez l’accès des utilisateurs distants, vous les activez pour l’ensemble de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="f6c5f-110">Si vous souhaitez empêcher l’accès des utilisateurs distants de manière temporaire ou définitive, vous pouvez le désactiver pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="f6c5f-111">Suivez la procédure décrite dans cette section pour activer ou désactiver l’accès des utilisateurs distants au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="f6c5f-112">L’activation de l’accès des utilisateurs distants indique uniquement que vos serveurs exécutant le service Edge d’accès prennent en charge les communications avec les utilisateurs distants, mais qu’ils ne peuvent pas participer à la messagerie instantanée ou aux conférences au sein de votre organisation tant que vous n’avez pas également configuré au moins une stratégie pour gérer l’utilisation de l’accès des utilisateurs distants.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="f6c5f-113">Les paramètres de stratégie de Skype entreprise Server appliqués à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="f6c5f-114">Le niveau de priorité de la stratégie de Skype entreprise Server est le suivant: la stratégie de l’utilisateur (la plus influence) remplace une stratégie de site, puis une stratégie de site remplace une stratégie globale (moins l’influence).</span><span class="sxs-lookup"><span data-stu-id="f6c5f-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="f6c5f-115">Cela signifie que le paramètre de stratégie est plus proche de l’objet affecté par la stratégie, plus l’influence sur l’objet.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="f6c5f-116">Pour plus d’informations sur la configuration des stratégies pour l’utilisation de l’accès des utilisateurs distants, voir [configurer des stratégies pour contrôler l’accès des utilisateurs distants dans Skype entreprise Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="f6c5f-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="f6c5f-117">Pour activer ou désactiver l’accès des utilisateurs distants pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="f6c5f-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="f6c5f-118">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f6c5f-119">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f6c5f-120">Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Configuration du serveur Edge d’accès**.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="f6c5f-121">Dans la page **configuration de Microsoft Edge** , cliquez sur **Global**, sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f6c5f-122">Dans **modification de la configuration d’Access Edge**, effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="f6c5f-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="f6c5f-123">Pour autoriser l’accès des utilisateurs distants pour votre organisation, activez la case à cocher **activer l’accès aux utilisateurs** distants.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="f6c5f-124">Pour désactiver l’accès des utilisateurs distants pour votre organisation, décochez la case **activer l’accès distant aux utilisateurs** .</span><span class="sxs-lookup"><span data-stu-id="f6c5f-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="f6c5f-125">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-125">Click **Commit**.</span></span>

<span data-ttu-id="f6c5f-126">Pour permettre aux utilisateurs distants de se connecter à des serveurs exécutant Skype entreprise Server, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs distants.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="f6c5f-127">Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies pour contrôler l’accès des utilisateurs distants dans Skype entreprise Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="f6c5f-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f6c5f-128">Activation ou désactivation de l’accès des utilisateurs distants à l’aide d’applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6c5f-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f6c5f-129">L’accès des utilisateurs distants peut être géré à l’aide de Windows PowerShell et de l’applet de commande Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="f6c5f-130">Ce cmdlet peut être exécuté à partir de Skype entreprise Server 2013 Management Shell ou d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6c5f-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="f6c5f-131">Pour autoriser l’accès des utilisateurs distants</span><span class="sxs-lookup"><span data-stu-id="f6c5f-131">To enable remote user access</span></span>

  - <span data-ttu-id="f6c5f-132">Pour autoriser l’accès des utilisateurs distants, définissez la valeur de la propriété **AllowOutsideUsers** sur True ($true):</span><span class="sxs-lookup"><span data-stu-id="f6c5f-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="f6c5f-133">Pour désactiver l’accès des utilisateurs distants</span><span class="sxs-lookup"><span data-stu-id="f6c5f-133">To disable remote user access</span></span>

  - <span data-ttu-id="f6c5f-134">Pour désactiver l’accès des utilisateurs distants, définissez la valeur de la propriété **AllowOutsideUsers** sur false ($false):</span><span class="sxs-lookup"><span data-stu-id="f6c5f-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


