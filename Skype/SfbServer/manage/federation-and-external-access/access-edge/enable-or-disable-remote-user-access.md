---
title: Activation ou désactivation de l’accès des utilisateurs distants
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si vous activez l’accès des utilisateurs distants pour les utilisateurs distants, pris en charge les utilisateurs distants se connectent via Internet et n’ont pas à se connecter à l’aide d’un réseau privé virtuel pour collaborer avec des utilisateurs internes à l’aide de Skype pour Business Server.
ms.openlocfilehash: 34733c4d1912461090ef868e24ae24dc1c870a94
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222876"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="8c608-103">Activer ou désactiver l’accès des utilisateurs distants dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="8c608-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="8c608-104">Les utilisateurs distants sont des utilisateurs de votre organisation qui ont une identité Active Directory persistante au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="8c608-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="8c608-105">Les utilisateurs distants souvent connectez-vous à Skype pour Business Server à partir d’en dehors de votre réseau à l’aide d’un réseau privé virtuel (VPN) lorsqu’ils ne sont pas connectés au réseau de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8c608-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="8c608-106">Les utilisateurs distants incluent les employés travaillant à domicile ou sur la route et d’autres travailleurs à distance, comme des fournisseurs approuvés, des informations d’identification de l’entreprise qui ont été accordées.</span><span class="sxs-lookup"><span data-stu-id="8c608-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="8c608-107">Si vous activez l’accès des utilisateurs distants pour les utilisateurs distants, pris en charge les utilisateurs distants se connectent via Internet et n’ont pas à se connecter à l’aide d’un réseau privé virtuel pour collaborer avec des utilisateurs internes à l’aide de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="8c608-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="8c608-108">Pour prendre en charge l’accès des utilisateurs distants, vous devez activer l’accès des utilisateurs distants.</span><span class="sxs-lookup"><span data-stu-id="8c608-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="8c608-109">Lorsque vous activez l’accès des utilisateurs distants, vous l’activez pour toute votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8c608-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="8c608-110">Si vous souhaitez ultérieurement à titre temporaire ou permanent empêcher l’accès des utilisateurs distants, vous pouvez le désactiver pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8c608-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="8c608-111">Utilisez la procédure de cette section pour activer ou désactiver l’accès des utilisateurs distants pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8c608-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="8c608-112">Activer l’accès des utilisateurs distants indique uniquement que vos serveurs exécutant le service Edge d’accès prennent en charge les communications avec les utilisateurs distants, mais les utilisateurs distants ne peut pas participer à la messagerie instantanée (MI) ou des conférences dans votre organisation jusqu'à ce que vous configurez également au au moins une stratégie pour gérer l’utilisation de l’accès des utilisateurs distants.</span><span class="sxs-lookup"><span data-stu-id="8c608-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="8c608-113">Skype pour les paramètres de stratégie Business Server qui sont appliqués à un niveau de stratégie permettre remplacer les paramètres qui sont appliqués au niveau de stratégie d’une autre.</span><span class="sxs-lookup"><span data-stu-id="8c608-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="8c608-114">Skype pour la priorité de la stratégie Business Server est : stratégie utilisateur (influencent la plupart) substitue à une stratégie de Site, puis une stratégie de Site substitue à une stratégie globale (influence moins).</span><span class="sxs-lookup"><span data-stu-id="8c608-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="8c608-115">Cela signifie que le paramètre de stratégie est proche de l’objet qui affecte la stratégie, la plus grande influence sur l’objet.</span><span class="sxs-lookup"><span data-stu-id="8c608-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="8c608-116">Pour plus d’informations sur la configuration de stratégies pour l’utilisation de l’accès des utilisateurs distants, voir [Configuration des stratégies pour contrôler l’accès des utilisateurs distants dans Skype pour Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="8c608-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="8c608-117">Pour activer ou désactiver l’accès des utilisateurs distants pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="8c608-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="8c608-118">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="8c608-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8c608-119">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="8c608-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8c608-120">Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Configuration du serveur Edge d’accès**.</span><span class="sxs-lookup"><span data-stu-id="8c608-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="8c608-121">Dans la page **Configuration du serveur Edge d’accès** , cliquez sur **Global**, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="8c608-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="8c608-122">Dans **Modifier la Configuration Edge accès**, effectuez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="8c608-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="8c608-123">Pour activer l’accès des utilisateurs distants pour votre organisation, activez la case à cocher **Activer l’accès des utilisateurs distants** .</span><span class="sxs-lookup"><span data-stu-id="8c608-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="8c608-124">Pour désactiver l’accès des utilisateurs distants pour votre organisation, désactivez la case à cocher **Activer l’accès des utilisateurs distants** .</span><span class="sxs-lookup"><span data-stu-id="8c608-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="8c608-125">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="8c608-125">Click **Commit**.</span></span>

<span data-ttu-id="8c608-126">Pour permettre aux utilisateurs distants de se connecter à vos serveurs exécutant Skype pour Business Server, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs distants.</span><span class="sxs-lookup"><span data-stu-id="8c608-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="8c608-127">Pour plus d’informations, voir [Configuration des stratégies pour contrôler l’accès des utilisateurs distants dans Skype pour Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="8c608-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8c608-128">Activation ou désactivation de l’accès des utilisateurs distants à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c608-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="8c608-129">Accès des utilisateurs distants peuvent être gérés à l’aide de Windows PowerShell et l’applet de commande Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="8c608-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="8c608-130">Cette applet de commande peut être exécutée à partir de la Skype pour Business Server 2013 Management Shell ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c608-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="8c608-131">Pour activer l’accès des utilisateurs distants</span><span class="sxs-lookup"><span data-stu-id="8c608-131">To enable remote user access</span></span>

  - <span data-ttu-id="8c608-132">Pour activer l’accès des utilisateurs distants, définissez la valeur de la propriété **AllowOutsideUsers** sur True ($True) :</span><span class="sxs-lookup"><span data-stu-id="8c608-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="8c608-133">Pour désactiver l’accès des utilisateurs distants</span><span class="sxs-lookup"><span data-stu-id="8c608-133">To disable remote user access</span></span>

  - <span data-ttu-id="8c608-134">Pour désactiver l’accès des utilisateurs distants, définissez la valeur de la propriété **AllowOutsideUsers** sur False ($False) :</span><span class="sxs-lookup"><span data-stu-id="8c608-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


