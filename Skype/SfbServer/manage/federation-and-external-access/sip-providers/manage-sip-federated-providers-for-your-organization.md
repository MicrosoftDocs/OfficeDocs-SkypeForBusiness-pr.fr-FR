---
title: Gestion des fournisseurs fédérés SIP pour l’organisation
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Découvrez comment configurer la prise en charge des utilisateurs de fournisseurs fédérés SIP.
ms.openlocfilehash: 42845bfd39c65e60765ee8d3fd2f1e3a58a08aae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818365"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="cdaf1-103">Gestion des fournisseurs fédérés SIP pour votre organisation dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cdaf1-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="cdaf1-104">Pour configurer la prise en charge des utilisateurs de fournisseurs fédérés SIP, vous devez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="cdaf1-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="cdaf1-105">Configuration d’une ou plusieurs stratégies d’accès des utilisateurs externes pour la prise en charge de la communication avec les contacts du fournisseur fédéré SIP</span><span class="sxs-lookup"><span data-stu-id="cdaf1-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="cdaf1-106">Spécifier les fournisseurs hébergés que vous voulez prendre en charge</span><span class="sxs-lookup"><span data-stu-id="cdaf1-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="cdaf1-107">Spécifier les fournisseurs de messagerie instantanée publics que vous voulez prendre en charge</span><span class="sxs-lookup"><span data-stu-id="cdaf1-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="cdaf1-108">Créer ou modifier des fournisseurs fédérés SIP publics dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cdaf1-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="cdaf1-109">La connectivité de messagerie instantanée publique permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs de services de messagerie instantanée proposés par des fournisseurs publics.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="cdaf1-110">Skype entreprise Server dispose de configurations de fournisseur public pour la messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="cdaf1-111">Chaque fournisseur public est configuré à l’aide du nom de domaine complet du serveur Edge du fournisseur et le niveau de vérification par défaut **permet aux utilisateurs de communiquer uniquement avec des personnes figurant sur leur liste de contacts qui utilisent ce fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="cdaf1-112">Comme paramètre par défaut, aucun des fournisseurs publics n’est activé.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="cdaf1-113">Vous devez compléter le contrat de licence et le fonctionnement de la mise en service avant d’activer les fournisseurs publics.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="cdaf1-114">Vous pouvez activer le fournisseur avant d’effectuer les tâches de gestion des licences et de mise en service.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="cdaf1-115">Les utilisateurs ne seront pas en mesure de communiquer avec les contacts de ces fournisseurs tant que la configuration requise ne sera pas effectuée.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="cdaf1-116">Pour plus d’informations sur la gestion des licences et la mise en service des fournisseurs publics, voir [configurer des stratégies pour contrôler les accès publiques aux utilisateurs](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="cdaf1-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="cdaf1-117">Utilisez la procédure suivante pour créer ou modifier des fournisseurs publics.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="cdaf1-118">Pour créer ou modifier des fournisseurs publics</span><span class="sxs-lookup"><span data-stu-id="cdaf1-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="cdaf1-119">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cdaf1-120">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="cdaf1-121">Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **fournisseurs fédérés SIP**.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="cdaf1-122">Si vous avez besoin de créer un nouveau fournisseur public, cliquez sur **nouveau** , puis cliquez sur **fournisseur public**.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="cdaf1-123">Si vous devez modifier une entrée dans la liste des fournisseurs publics, sélectionnez un fournisseur public, cliquez sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="cdaf1-124">Dans la page **modifier le fournisseur fédéré SIP** , vous pouvez taper ou modifier les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="cdaf1-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="cdaf1-125">**Activer les communications avec ce fournisseur**   sélectionnez ce paramètre active la messagerie instantanée avec les utilisateurs de ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="cdaf1-126">**Nom du fournisseur :**   une propriété requise, tapez le nom du fournisseur tel qu’il sera reflété dans la liste des fournisseurs fédérés SIP.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="cdaf1-127">**Service Edge d’accès (FQDN) :**   une propriété requise, tapez le nom de domaine complet du service Edge d’accès du fournisseur que vous configurez.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="cdaf1-128">Ces informations sont fournies en tant qu’élément par défaut et ne doivent être changées que si le fournisseur public apporte une modification au FQDN du service Edge d’accès au fournisseur public.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="cdaf1-129">**Niveau de vérification par défaut :**   le paramètre par défaut, **permettre aux utilisateurs de communiquer avec des personnes de la liste de contacts qui utilisent ce fournisseur** , limite les communications aux contacts que vous avez acceptés et qui se trouvent dans votre liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="cdaf1-130">Sélectionner **permettre aux utilisateurs de communiquer avec tout le monde à l’aide de ce fournisseur** supprime la restriction que vous devez avoir reçu et accepté une invitation de contact.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-130">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="cdaf1-131">Ce paramètre ne limite pas les personnes qui peuvent vous contacter à partir du réseau du fournisseur public.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-131">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="cdaf1-132">Lorsque vous avez configuré les paramètres, cliquez sur **valider** pour enregistrer ou cliquez sur **Annuler** pour ignorer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="cdaf1-133">Créer ou modifier des fournisseurs fédérés SIP hébergés dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cdaf1-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="cdaf1-134">La connectivité de messagerie instantanée du fournisseur hébergé permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs de services de messagerie instantanée proposés par des fournisseurs hébergés.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="cdaf1-135">Chaque fournisseur hébergé est configuré à l’aide du nom de domaine complet du serveur Edge du fournisseur, et le niveau de vérification par défaut **permet aux utilisateurs de communiquer uniquement avec des personnes de leur liste de contacts qui utilisent ce fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="cdaf1-136">Utilisez la procédure suivante pour créer ou modifier des fournisseurs hébergés.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="cdaf1-137">Pour créer ou modifier des fournisseurs hébergés</span><span class="sxs-lookup"><span data-stu-id="cdaf1-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="cdaf1-138">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cdaf1-139">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="cdaf1-140">Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **fournisseurs fédérés SIP**.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="cdaf1-141">Si vous avez besoin de créer un nouveau fournisseur hébergé, cliquez sur **nouveau** , puis cliquez sur **fournisseur hébergé**.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="cdaf1-142">Si vous avez besoin de modifier une entrée de la liste des fournisseurs hébergés, sélectionnez un fournisseur hébergé, cliquez sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="cdaf1-143">Dans la page **modifier le fournisseur fédéré SIP** , vous pouvez taper ou modifier les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="cdaf1-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="cdaf1-144">**Activer les communications avec ce fournisseur**   sélectionnez ce paramètre active les communications avec les utilisateurs de ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="cdaf1-145">**Nom du fournisseur :**   une propriété requise, tapez le nom du fournisseur tel qu’il sera reflété dans la liste des fournisseurs fédérés SIP.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="cdaf1-146">**Service Edge d’accès (FQDN) :**   une propriété requise, tapez le nom de domaine complet du service Edge d’accès du fournisseur hébergé que vous configurez.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="cdaf1-147">Ces informations doivent être fournies par le fournisseur hébergé et ne doivent être changées que si le fournisseur hébergé apporte une modification au FQDN du service Edge d’accès au fournisseur hébergé.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="cdaf1-148">**Niveau de vérification par défaut :**   le paramètre par défaut, **permettre aux utilisateurs de communiquer avec des personnes de la liste de contacts qui utilisent ce fournisseur** , limite les communications aux contacts que vous avez acceptés et qui se trouvent dans votre liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="cdaf1-149">Sélectionner **permettre aux utilisateurs de communiquer avec tout le monde à l’aide de ce fournisseur** supprime la restriction que vous devez avoir reçu et accepté une invitation de contact.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-149">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="cdaf1-150">Ce paramètre ne limite pas qui peut vous contacter à partir du réseau du fournisseur hébergé.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-150">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="cdaf1-151">Lorsque vous avez configuré les paramètres, cliquez sur **valider** pour enregistrer ou cliquez sur **Annuler** pour ignorer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="cdaf1-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="cdaf1-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cdaf1-152">See Also</span></span>


[<span data-ttu-id="cdaf1-153">Configurer des stratégies pour contrôler les accès public aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="cdaf1-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="cdaf1-154">Activation ou désactivation de la fédération et de la connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="cdaf1-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

