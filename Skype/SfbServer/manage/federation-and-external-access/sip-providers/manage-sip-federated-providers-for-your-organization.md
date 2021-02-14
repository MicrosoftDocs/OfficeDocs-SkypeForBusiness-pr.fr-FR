---
title: Gestion des fournisseurs fédérés SIP pour votre organisation
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
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
description: Découvrez comment configurer la prise en charge des utilisateurs de fournisseurs fédérés SIP.
ms.openlocfilehash: 8d4c6224a66454f8fb28bb4f991faf6ad672f596
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823564"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="58c90-103">Gérer les fournisseurs fédérés SIP pour votre organisation dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="58c90-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="58c90-104">Pour configurer la prise en charge pour les utilisateurs des fournisseurs fédérés SIP, vous devez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="58c90-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="58c90-105">Configurez une ou plusieurs des stratégies d’accès des utilisateurs externes pour prendre en charge la communication avec les contacts de fournisseurs fédérés SIP.</span><span class="sxs-lookup"><span data-stu-id="58c90-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="58c90-106">Spécifiez les fournisseurs hébergés à prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="58c90-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="58c90-107">Spécifiez les fournisseurs de messagerie instantanée publics à prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="58c90-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="58c90-108">Créer ou modifier des fournisseurs fédérés SIP publics dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="58c90-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="58c90-109">La connectivité de messagerie instantanée publique permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs des services de messagerie instantanée fournis par des fournisseurs publics.</span><span class="sxs-lookup"><span data-stu-id="58c90-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="58c90-110">Skype Entreprise Server dispose de configurations de fournisseur public pour la messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="58c90-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="58c90-111">Chaque fournisseur public est configuré avec le nom de domaine complet du serveur Edge du fournisseur et le niveau de vérification par défaut permet aux utilisateurs de communiquer uniquement avec les personnes de leur liste de contacts qui utilisent ce **fournisseur.**</span><span class="sxs-lookup"><span data-stu-id="58c90-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="58c90-112">Par défaut, aucun des fournisseurs publics n’est activé.</span><span class="sxs-lookup"><span data-stu-id="58c90-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="58c90-113">Terminez le travail relatif au contrat de licence et à l’approvisionnement avant d’activer les fournisseurs publics.</span><span class="sxs-lookup"><span data-stu-id="58c90-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="58c90-114">Vous pouvez activer le fournisseur avant de terminer le travail relatif au contrat de licence et à l’approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="58c90-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="58c90-115">Les utilisateurs ne pourront pas communiquer avec leurs contacts situés chez ces fournisseurs tant que le travail préalable ne sera pas terminé.</span><span class="sxs-lookup"><span data-stu-id="58c90-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="58c90-116">Pour plus d’informations sur la gestion des licences et l’approvisionnement des fournisseurs publics, voir Configurer des stratégies pour contrôler les accès [des utilisateurs publics.](../external-access-policies/configure-policies-to-control-public-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="58c90-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="58c90-117">Utilisez la procédure suivante pour créer ou modifier des fournisseurs publics.</span><span class="sxs-lookup"><span data-stu-id="58c90-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="58c90-118">Pour créer ou modifier des fournisseurs publics</span><span class="sxs-lookup"><span data-stu-id="58c90-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="58c90-119">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="58c90-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="58c90-120">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="58c90-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="58c90-121">Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Fournisseurs fédérés SIP**.</span><span class="sxs-lookup"><span data-stu-id="58c90-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="58c90-122">Pour créer un fournisseur public, cliquez sur **Nouveau**, puis sur **Fournisseur public**.</span><span class="sxs-lookup"><span data-stu-id="58c90-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="58c90-123">Si vous devez modifier une entrée dans la liste des fournisseurs publics, sélectionnez un fournisseur public, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="58c90-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="58c90-124">Dans la page **Modifier le fournisseur fédéré SIP**, vous pouvez taper ou modifier les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="58c90-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="58c90-125">**Activer les communications avec ce fournisseur**   La sélection de ce paramètre permet aux utilisateurs de ce fournisseur d’accéder à la messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="58c90-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="58c90-126">**Nom du fournisseur :** propriété requise. Tapez le nom du fournisseur tel qu’il apparaîtra dans la liste des fournisseurs fédérés SIP.</span><span class="sxs-lookup"><span data-stu-id="58c90-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="58c90-127">**Service Edge d’accès (FQDN) :**   Propriété obligatoire, tapez le nom de domaine complet du service Edge d’accès du fournisseur que vous configurez.</span><span class="sxs-lookup"><span data-stu-id="58c90-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="58c90-128">Ces informations sont fournies par défaut et ne doivent être changées que si le fournisseur public modifie le nom de domaine complet du service Edge d’accès au niveau du fournisseur public.</span><span class="sxs-lookup"><span data-stu-id="58c90-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="58c90-129">**Niveau de vérification par défaut :** le paramètre par défaut, **Autoriser les utilisateurs à communiquer avec les personnes dans leur liste des contacts qui utilisent ce fournisseur** limite la communication aux contacts que vous avez acceptés et qui figurent dans votre liste des contacts.</span><span class="sxs-lookup"><span data-stu-id="58c90-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="58c90-p104">La sélection du paramètre **Autoriser les utilisateurs à communiquer avec toutes les personnes qui utilisent ce fournisseur** supprime la restriction que vous devez avoir reçue et permet d’accepter l’invitation d’un contact. Ce paramètre n’impose pas de limite aux personnes qui peuvent vous contacter à partir du réseau du fournisseur public.</span><span class="sxs-lookup"><span data-stu-id="58c90-p104">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="58c90-132">Quand vous avez terminé de configurer les paramètres, cliquez sur **Valider** pour les enregistrer ou sur **Annuler** pour annuler vos modifications.</span><span class="sxs-lookup"><span data-stu-id="58c90-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="58c90-133">Créer ou modifier des fournisseurs fédérés SIP hébergés dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="58c90-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="58c90-134">La connectivité de messagerie instantanée du fournisseur hébergé permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs des services de messagerie instantanée fournis par des fournisseurs hébergés.</span><span class="sxs-lookup"><span data-stu-id="58c90-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="58c90-135">Chaque fournisseur hébergé est configuré avec le nom de domaine complet du serveur Edge du fournisseur et le niveau de vérification par défaut **Autoriser les utilisateurs à communiquer avec les personnes dans leur liste des contacts qui utilisent ce fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="58c90-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="58c90-136">Utilisez la procédure suivante pour créer ou modifier des fournisseurs hébergés.</span><span class="sxs-lookup"><span data-stu-id="58c90-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="58c90-137">Pour créer ou modifier des fournisseurs hébergés</span><span class="sxs-lookup"><span data-stu-id="58c90-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="58c90-138">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="58c90-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="58c90-139">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="58c90-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="58c90-140">Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Fournisseurs fédérés SIP**.</span><span class="sxs-lookup"><span data-stu-id="58c90-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="58c90-141">Si vous devez créer un nouveau fournisseur hébergé, cliquez sur **Nouveau**, puis sur **Fournisseur hébergé**.</span><span class="sxs-lookup"><span data-stu-id="58c90-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="58c90-142">Si vous devez modifier une entrée dans la liste des fournisseurs hébergés, sélectionnez un fournisseur hébergé, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="58c90-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="58c90-143">Dans la page **Modifier le fournisseur fédéré SIP**, vous pouvez taper ou modifier les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="58c90-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="58c90-144">**Activer les communications avec ce fournisseur** Ce paramètre active les communications avec les utilisateurs de ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="58c90-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="58c90-145">**Nom du fournisseur :** propriété requise. Tapez le nom du fournisseur tel qu’il apparaîtra dans la liste des fournisseurs fédérés SIP.</span><span class="sxs-lookup"><span data-stu-id="58c90-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="58c90-146">**Service Edge d’accès (FQDN) :**   Propriété obligatoire, tapez le nom de domaine complet du service Edge d’accès du fournisseur hébergé que vous configurez.</span><span class="sxs-lookup"><span data-stu-id="58c90-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="58c90-147">Cette information doit être fournie par le fournisseur hébergée et ne doit être modifiée que si le fournisseur hébergé modifie le nom de domaine complet de son service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="58c90-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="58c90-148">**Niveau de vérification par défaut :** le paramètre par défaut **Autoriser les utilisateurs à communiquer avec les personnes dans leur liste des contacts qui utilisent ce fournisseur** limite la communication aux contacts que vous avez acceptés et qui figurent dans votre liste des contacts.</span><span class="sxs-lookup"><span data-stu-id="58c90-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="58c90-p106">Sélectionnez **Autoriser les utilisateurs à communiquer avec toutes les personnes qui utilisent ce fournisseur** pour supprimer la restriction sur la réception et l’acceptation d’invitations de contacts. Ce paramètre n’applique aucune restriction sur les personnes qui peuvent vous contacter à partir du réseau du fournisseur hébergé.</span><span class="sxs-lookup"><span data-stu-id="58c90-p106">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="58c90-151">Une fois que vous avez configuré les paramètres, cliquez sur **Valider** pour les enregistrer ou sur **Annuler** pour annuler vos modifications.</span><span class="sxs-lookup"><span data-stu-id="58c90-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="58c90-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="58c90-152">See Also</span></span>


[<span data-ttu-id="58c90-153">Configurer des stratégies pour contrôler les accès des utilisateurs publics</span><span class="sxs-lookup"><span data-stu-id="58c90-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="58c90-154">Activation ou désactivation de la fédération et de la connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="58c90-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

