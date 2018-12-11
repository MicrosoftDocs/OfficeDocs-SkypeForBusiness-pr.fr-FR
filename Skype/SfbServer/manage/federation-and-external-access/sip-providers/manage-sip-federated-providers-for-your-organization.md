---
title: Gestion des fournisseurs fédérés SIP pour l’organisation
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Découvrez comment configurer la prise en charge pour les utilisateurs de SIP des fournisseurs fédérés.
ms.openlocfilehash: 111a71f95f3ae6a6c9dec90f5c0b29df07266fd2
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222960"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="4244c-103">Gérer les fournisseurs fédérés SIP de votre organisation dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="4244c-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="4244c-104">Pour configurer la prise en charge pour les utilisateurs de SIP des fournisseurs fédérés, vous devez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4244c-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="4244c-105">Configurez une ou plusieurs stratégies d’accès utilisateur externe pour prendre en charge la communication avec des contacts fédérés SIP fournisseur</span><span class="sxs-lookup"><span data-stu-id="4244c-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="4244c-106">Spécifiez les fournisseurs hébergés que vous souhaitez prendre en charge</span><span class="sxs-lookup"><span data-stu-id="4244c-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="4244c-107">Spécifier les fournisseurs de messagerie instantanée publics que vous souhaitez prendre en charge</span><span class="sxs-lookup"><span data-stu-id="4244c-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="4244c-108">Créer ou modifier des fournisseurs fédérés SIP publics dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="4244c-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="4244c-109">Connectivité de messagerie instantanée publique permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs des services de messagerie instantanée fournis par les fournisseurs publics.</span><span class="sxs-lookup"><span data-stu-id="4244c-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="4244c-110">Skype pour Business Server possède des configurations de fournisseur public pour la messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="4244c-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="4244c-111">Chaque fournisseur public est configuré avec le nom de domaine complet de serveur Edge du fournisseur et le niveau de vérification par défaut **Autoriser les utilisateurs à communiquer avec des personnes dans leur liste de Contacts qui utilisent ce fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="4244c-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="4244c-112">Par défaut, aucun des fournisseurs publics sont activés.</span><span class="sxs-lookup"><span data-stu-id="4244c-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="4244c-113">Vous devez effectuer le contrat de licence et de mise en service du travail avant d’activer les fournisseurs publics.</span><span class="sxs-lookup"><span data-stu-id="4244c-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="4244c-114">Vous pouvez activer le fournisseur avant la fin de la gestion des licences et de mise en service du travail.</span><span class="sxs-lookup"><span data-stu-id="4244c-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="4244c-115">Les utilisateurs ne pourront pas communiquer avec des contacts sur les fournisseurs jusqu'à ce que le travail requis est terminé.</span><span class="sxs-lookup"><span data-stu-id="4244c-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="4244c-116">Pour plus d’informations sur la gestion des licences et la configuration des fournisseurs publics, consultez [configurer les stratégies pour contrôler l’accès des utilisateurs publics](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="4244c-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="4244c-117">Utilisez la procédure suivante pour créer ou modifier des fournisseurs publics.</span><span class="sxs-lookup"><span data-stu-id="4244c-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="4244c-118">Pour créer ou modifier des fournisseurs publics</span><span class="sxs-lookup"><span data-stu-id="4244c-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="4244c-119">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="4244c-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4244c-120">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="4244c-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4244c-121">Dans la barre de navigation de gauche, cliquez sur **fédération et accès externe**, puis cliquez sur **Fournisseurs fédérés SIP**.</span><span class="sxs-lookup"><span data-stu-id="4244c-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="4244c-122">Si vous avez besoin créer un nouveau fournisseur Public, cliquez sur **Nouveau** , puis sur **fournisseur Public**.</span><span class="sxs-lookup"><span data-stu-id="4244c-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="4244c-123">Si vous devez modifier une entrée de la liste des fournisseurs publics, sélectionnez un fournisseur public, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="4244c-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="4244c-124">Dans la page **Modifier un fournisseur fédéré SIP** , vous pouvez taper ou modifier les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="4244c-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="4244c-125">**Activer les communications avec ce fournisseur**   ce paramètre permet de messagerie instantanée avec des utilisateurs de ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="4244c-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="4244c-126">**Nom du fournisseur :**   une propriété requise, le type du nom du fournisseur tel qu’il apparaîtra dans la liste des fournisseurs fédérés SIP.</span><span class="sxs-lookup"><span data-stu-id="4244c-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="4244c-127">**Service Edge (FQDN) d’accès :**   propriété obligatoire, tapez le nom de domaine complet du service Edge d’accès du fournisseur que vous configurez.</span><span class="sxs-lookup"><span data-stu-id="4244c-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="4244c-128">Ces informations fournies sous la forme d’un élément par défaut et doivent être modifiées seulement si le fournisseur public modifie le nom de domaine complet du service Edge d’accès au niveau du fournisseur public.</span><span class="sxs-lookup"><span data-stu-id="4244c-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="4244c-129">**Niveau de vérification par défaut :**   le paramètre par défaut, **Autoriser les utilisateurs à communiquer avec les personnes à leur liste de Contacts qui utilisent ce fournisseur** permet de limiter la communication à des contacts que vous avez accepté et se trouvent dans votre liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="4244c-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="4244c-130">Sélectionnez **Autoriser les utilisateurs à communiquer avec tout le monde à l’aide de ce fournisseur** supprime la restriction, vous devez avoir reçu et accepté une invitation à un contact.</span><span class="sxs-lookup"><span data-stu-id="4244c-130">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="4244c-131">Ce paramètre ne limite pas qui peuvent vous contacter à partir du réseau du fournisseur public.</span><span class="sxs-lookup"><span data-stu-id="4244c-131">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="4244c-132">Lorsque vous avez la définition des paramètres, cliquez sur **Valider** pour enregistrer ou cliquez sur **Annuler** pour ignorer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="4244c-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="4244c-133">Créer ou modifier des fournisseurs fédérés SIP hébergés dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="4244c-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="4244c-134">Hébergée (IM) connectivité permet aux utilisateurs de votre organisation pour utiliser la messagerie instantanée pour communiquer avec les utilisateurs des services de messagerie instantanée fournis par des fournisseurs hébergés de messagerie instantanée de fournisseur.</span><span class="sxs-lookup"><span data-stu-id="4244c-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="4244c-135">Chaque fournisseur hébergé est configuré avec le nom de domaine complet de serveur Edge du fournisseur et le niveau de vérification par défaut **Autoriser les utilisateurs à communiquer avec des personnes dans leur liste de Contacts qui utilisent ce fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="4244c-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="4244c-136">Utilisez la procédure suivante pour créer ou modifier des fournisseurs hébergés.</span><span class="sxs-lookup"><span data-stu-id="4244c-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="4244c-137">Pour créer ou modifier des fournisseurs hébergés</span><span class="sxs-lookup"><span data-stu-id="4244c-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="4244c-138">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="4244c-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4244c-139">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="4244c-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4244c-140">Dans la barre de navigation de gauche, cliquez sur **fédération et accès externe**, puis cliquez sur **Fournisseurs fédérés SIP**.</span><span class="sxs-lookup"><span data-stu-id="4244c-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="4244c-141">Si vous avez besoin créer un nouveau fournisseur hébergé, cliquez sur **Nouveau** , puis sur **fournisseur hébergé**.</span><span class="sxs-lookup"><span data-stu-id="4244c-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="4244c-142">Si vous devez modifier une entrée de la liste des fournisseurs hébergés, sélectionnez un fournisseur hébergé, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="4244c-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="4244c-143">Dans la page **Modifier un fournisseur fédéré SIP** , vous pouvez taper ou modifier les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="4244c-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="4244c-144">**Activer les communications avec ce fournisseur**   ce paramètre active les communications avec les utilisateurs de ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="4244c-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="4244c-145">**Nom du fournisseur :**   une propriété requise, le type du nom du fournisseur tel qu’il apparaîtra dans la liste des fournisseurs fédérés SIP.</span><span class="sxs-lookup"><span data-stu-id="4244c-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="4244c-146">**Service Edge (FQDN) d’accès :**   propriété obligatoire, tapez le nom de domaine complet du service Edge d’accès du fournisseur hébergé que vous configurez.</span><span class="sxs-lookup"><span data-stu-id="4244c-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="4244c-147">Ces informations doivent être fournies par le fournisseur hébergé et doivent être modifiées seulement si le fournisseur hébergé modifie le nom de domaine complet du service Edge d’accès au niveau du fournisseur hébergé.</span><span class="sxs-lookup"><span data-stu-id="4244c-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="4244c-148">**Niveau de vérification par défaut :**   le paramètre par défaut, **Autoriser les utilisateurs à communiquer avec les personnes à leur liste de Contacts qui utilisent ce fournisseur** permet de limiter la communication à des contacts que vous avez accepté et se trouvent dans votre liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="4244c-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="4244c-149">Sélectionnez **Autoriser les utilisateurs à communiquer avec tout le monde à l’aide de ce fournisseur** supprime la restriction, vous devez avoir reçu et accepté une invitation à un contact.</span><span class="sxs-lookup"><span data-stu-id="4244c-149">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="4244c-150">Ce paramètre ne limite pas qui peuvent vous contacter à partir du réseau du fournisseur hébergé.</span><span class="sxs-lookup"><span data-stu-id="4244c-150">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="4244c-151">Lorsque vous avez la définition des paramètres, cliquez sur **Valider** pour enregistrer ou cliquez sur **Annuler** pour ignorer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="4244c-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="4244c-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4244c-152">See Also</span></span>


[<span data-ttu-id="4244c-153">Configurer des stratégies pour contrôler l’accès des utilisateurs publics</span><span class="sxs-lookup"><span data-stu-id="4244c-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="4244c-154">Activation ou désactivation de la fédération et de la connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="4244c-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

