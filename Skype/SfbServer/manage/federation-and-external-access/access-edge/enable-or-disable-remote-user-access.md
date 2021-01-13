---
title: Activation ou désactivation de l’accès utilisateur distant
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
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
description: Si vous activez l’accès des utilisateurs distants pour les utilisateurs distants, les utilisateurs distants pris en charge se connectent via Internet et n’ont pas besoin de se connecter à l’aide d’un VPN pour collaborer avec des utilisateurs internes à l’aide de Skype Entreprise Server.
ms.openlocfilehash: 9e5ba5828e129c6fed5dd892b1a7bb8e6bd64707
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817394"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="eb8cb-103">Activer ou désactiver l’accès des utilisateurs distants dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="eb8cb-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="eb8cb-104">Les utilisateurs distants sont des utilisateurs de votre organisation qui ont une identité Active Directory persistante au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="eb8cb-105">Les utilisateurs distants se connectent souvent à Skype Entreprise Server depuis l’extérieur de votre réseau à l’aide d’un réseau privé virtuel (VPN) lorsqu’ils ne sont pas connectés au réseau de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="eb8cb-106">Les utilisateurs distants incluent les employés travaillant à domicile ou sur la route, ainsi que d’autres travailleurs à distance, tels que des fournisseurs de confiance, qui ont reçu des informations d’identification d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="eb8cb-107">Si vous activez l’accès des utilisateurs distants pour les utilisateurs distants, les utilisateurs distants pris en charge se connectent via Internet et n’ont pas besoin de se connecter à l’aide d’un VPN pour collaborer avec des utilisateurs internes à l’aide de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="eb8cb-p102">Pour prendre en charge l’accès des utilisateurs distants, vous devez l’activer (pour l’ensemble de votre entreprise). Si vous souhaitez plus tard empêcher temporairement ou définitivement l’accès des utilisateurs distants, vous pouvez le désactiver pour votre entreprise. Suivez la procédure dans cette section pour activer ou désactiver l’accès des utilisateurs distants pour votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-p102">To support remote user access, you must enable remote user access. When you enable remote user access, you enable it for your entire organization. If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization. Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="eb8cb-112">L’activation de l’accès des utilisateurs distants spécifie uniquement que vos serveurs exécutant le service Edge d’accès gèrent les communications avec des utilisateurs distants, mais que les utilisateurs distants ne peuvent pas participer à des conférences ou des messages instantanés dans votre organisation tant que vous n’avez pas configuré au moins une stratégie pour gérer l’utilisation de l’accès des utilisateurs distants.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="eb8cb-113">Les paramètres de stratégie Skype Entreprise Server appliqués à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="eb8cb-114">La politique de priorité de Skype Entreprise Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente).</span><span class="sxs-lookup"><span data-stu-id="eb8cb-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="eb8cb-115">Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="eb8cb-116">Pour plus d’informations sur la configuration des stratégies pour l’utilisation de l’accès des utilisateurs distants, voir Configurer des stratégies pour contrôler l’accès des utilisateurs distants [dans Skype Entreprise Server.](../external-access-policies/configure-policies-to-control-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="eb8cb-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="eb8cb-117">Pour activer ou désactiver l’accès des utilisateurs distants pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="eb8cb-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="eb8cb-118">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="eb8cb-119">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="eb8cb-120">Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Configuration du serveur Edge d’accès**.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="eb8cb-121">Sur la page **Configuration du serveur Edge d’accès**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="eb8cb-122">Dans **Modifier la configuration du serveur Edge d’accès**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="eb8cb-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="eb8cb-123">Pour activer l’accès des utilisateurs distants pour votre entreprise, activez la case à cocher **Activer l’accès des utilisateurs distants**.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="eb8cb-124">Pour désactiver l’accès des utilisateurs distants pour votre entreprise, désactivez la case à cocher **Activer l’accès des utilisateurs distants**.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="eb8cb-125">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-125">Click **Commit**.</span></span>

<span data-ttu-id="eb8cb-126">Pour permettre aux utilisateurs distants de se connectent à vos serveurs exécutant Skype Entreprise Server, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs distants.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="eb8cb-127">Pour plus d’informations, voir Configurer des stratégies pour contrôler l’accès des utilisateurs [distants dans Skype Entreprise Server.](../external-access-policies/configure-policies-to-control-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="eb8cb-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="eb8cb-128">Activation ou désactivation de l’accès des utilisateurs distants à l’Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="eb8cb-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="eb8cb-129">L’accès des utilisateurs distants peut être géré à l’Windows PowerShell l'Set-CsAccessEdgeConfiguration cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="eb8cb-130">Cette cmdlet peut être exécuté à partir de Skype Entreprise Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="eb8cb-131">Pour activer l’accès des utilisateurs distants</span><span class="sxs-lookup"><span data-stu-id="eb8cb-131">To enable remote user access</span></span>

  - <span data-ttu-id="eb8cb-132">Pour activer l’accès des utilisateurs distants, définissez la valeur de la propriété **AllowOutsideUsers** sur True ($True) :</span><span class="sxs-lookup"><span data-stu-id="eb8cb-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="eb8cb-133">Pour désactiver l’accès des utilisateurs distants</span><span class="sxs-lookup"><span data-stu-id="eb8cb-133">To disable remote user access</span></span>

  - <span data-ttu-id="eb8cb-134">Pour désactiver l’accès des utilisateurs distants, définissez la valeur de la propriété **AllowOutsideUsers** sur False ($False) :</span><span class="sxs-lookup"><span data-stu-id="eb8cb-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


