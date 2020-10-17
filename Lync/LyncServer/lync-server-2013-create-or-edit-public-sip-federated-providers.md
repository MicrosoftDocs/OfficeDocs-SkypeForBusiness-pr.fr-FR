---
title: 'Lync Server 2013 : création ou modification des fournisseurs fédérés SIP publics'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58b0ffdc009d48ef82d1bdf3ba8662cd4072ea1c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514851"
---
# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a><span data-ttu-id="5f923-102">Création ou modification de fournisseurs fédérés SIP publics dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f923-102">Create or edit public SIP federated providers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f923-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="5f923-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="5f923-104">La connectivité PIC (Public IM Connectivity) permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs de services de messagerie instantanée fournis par des fournisseurs de services de messagerie instantanée publics, notamment Windows Live Messenger, Yahoo \! et AOL.</span><span class="sxs-lookup"><span data-stu-id="5f923-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live Messenger, Yahoo\!, and AOL.</span></span>

<span data-ttu-id="5f923-105">Lync Server 2013 possède des configurations de fournisseur public pour America Online, Windows Live et Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="5f923-105">Lync Server 2013 has public provider configurations for America Online, Windows Live and Yahoo\!</span></span> <span data-ttu-id="5f923-106">messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="5f923-106">instant messaging.</span></span> <span data-ttu-id="5f923-107">Chaque fournisseur public est configuré avec le nom de domaine complet du serveur Edge du fournisseur et le niveau de vérification par défaut **permet aux utilisateurs de communiquer uniquement avec des personnes de leur liste de contacts qui utilisent ce fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="5f923-107">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="5f923-108">Par défaut, aucun des fournisseurs publics n’est activé.</span><span class="sxs-lookup"><span data-stu-id="5f923-108">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="5f923-109">Terminez le travail relatif au contrat de licence et à l’approvisionnement avant d’activer les fournisseurs publics.</span><span class="sxs-lookup"><span data-stu-id="5f923-109">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="5f923-110">Vous pouvez activer le fournisseur avant de terminer le travail relatif au contrat de licence et à l’approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="5f923-110">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="5f923-111">Les utilisateurs ne pourront pas communiquer avec leurs contacts situés chez ces fournisseurs tant que le travail préalable ne sera pas terminé.</span><span class="sxs-lookup"><span data-stu-id="5f923-111">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="5f923-112">Pour plus d’informations sur la gestion des licences et la mise en service des fournisseurs publics, voir [configure Policies to Control public user Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="5f923-112">For details on licensing and provisioning of public providers, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="5f923-113">Procédez comme suit pour créer ou modifier des fournisseurs publics :</span><span class="sxs-lookup"><span data-stu-id="5f923-113">Use the following procedure to create or edit Public providers:</span></span>

<div>

## <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="5f923-114">Pour créer ou modifier des fournisseurs publics</span><span class="sxs-lookup"><span data-stu-id="5f923-114">To create or edit public providers</span></span>

1.  <span data-ttu-id="5f923-115">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="5f923-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5f923-116">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f923-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5f923-117">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5f923-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5f923-118">Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Fournisseurs fédérés SIP**.</span><span class="sxs-lookup"><span data-stu-id="5f923-118">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="5f923-119">Pour créer un fournisseur public, cliquez sur **Nouveau**, puis sur **Fournisseur public**.</span><span class="sxs-lookup"><span data-stu-id="5f923-119">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="5f923-120">Si vous devez modifier une entrée dans la liste des fournisseurs publics, sélectionnez un fournisseur public, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="5f923-120">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="5f923-121">Dans la page **Modifier le fournisseur fédéré SIP**, vous pouvez taper ou modifier les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5f923-121">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="5f923-122">**Activer les communications avec ce fournisseur**     La sélection de ce paramètre active la messagerie instantanée avec les utilisateurs de ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="5f923-122">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="5f923-123">**Nom du fournisseur :**     Une propriété obligatoire, tapez le nom du fournisseur tel qu’il apparaîtra dans la liste des fournisseurs fédérés SIP.</span><span class="sxs-lookup"><span data-stu-id="5f923-123">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="5f923-124">**Service Edge d’accès (FQDN) :**     Une propriété obligatoire, tapez le nom de domaine complet du service Edge d’accès du fournisseur que vous configurez.</span><span class="sxs-lookup"><span data-stu-id="5f923-124">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="5f923-125">Ces informations sont fournies par défaut et ne doivent être changées que si le fournisseur public modifie le nom de domaine complet du service Edge d’accès au niveau du fournisseur public.</span><span class="sxs-lookup"><span data-stu-id="5f923-125">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="5f923-126">**Niveau de vérification par défaut :**     Le paramètre par défaut, **autoriser les utilisateurs à communiquer avec des personnes de leur liste de contacts qui utilisent ce fournisseur** , limite la communication aux contacts que vous avez acceptés et se trouve dans votre liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="5f923-126">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="5f923-p105">La sélection du paramètre **Autoriser les utilisateurs à communiquer avec toutes les personnes qui utilisent ce fournisseur** supprime la restriction que vous devez avoir reçue et permet d’accepter l’invitation d’un contact. Ce paramètre n’impose pas de limite aux personnes qui peuvent vous contacter à partir du réseau du fournisseur public.</span><span class="sxs-lookup"><span data-stu-id="5f923-p105">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="5f923-129">Quand vous avez terminé de configurer les paramètres, cliquez sur **Valider** pour les enregistrer ou sur **Annuler** pour annuler vos modifications.</span><span class="sxs-lookup"><span data-stu-id="5f923-129">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5f923-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5f923-130">See Also</span></span>


[<span data-ttu-id="5f923-131">Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f923-131">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="5f923-132">Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f923-132">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

