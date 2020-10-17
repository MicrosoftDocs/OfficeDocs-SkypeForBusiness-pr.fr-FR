---
title: 'Lync Server 2013 : création ou modification des fournisseurs fédérés SIP hébergés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7704074db1b210ca341b05df9fbd02afabbc70a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507491"
---
# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a><span data-ttu-id="e9216-102">Créer ou modifier des fournisseurs fédérés SIP hébergés Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9216-102">Create or edit hosted SIP federated providers Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9216-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e9216-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e9216-104">La connectivité de messagerie instantanée des fournisseurs hébergés permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec des utilisateurs de services de messagerie instantanée fournis par des fournisseurs hébergés, notamment Microsoft 365 et Lync Online.</span><span class="sxs-lookup"><span data-stu-id="e9216-104">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers, including Microsoft 365 and Lync Online.</span></span>

<span data-ttu-id="e9216-105">Chaque fournisseur hébergé est configuré avec le nom de domaine complet du serveur Edge du fournisseur et le niveau de vérification par défaut **Autoriser les utilisateurs à communiquer avec les personnes dans leur liste des contacts qui utilisent ce fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="e9216-105">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="e9216-106">Procédez comme suit pour créer ou modifier des fournisseurs hébergés :</span><span class="sxs-lookup"><span data-stu-id="e9216-106">Use the following procedure to create or edit Hosted providers:</span></span>

<div>

## <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="e9216-107">Pour créer ou modifier des fournisseurs hébergés</span><span class="sxs-lookup"><span data-stu-id="e9216-107">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="e9216-108">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="e9216-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e9216-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e9216-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e9216-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e9216-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e9216-111">Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Fournisseurs fédérés SIP**.</span><span class="sxs-lookup"><span data-stu-id="e9216-111">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="e9216-112">Si vous devez créer un nouveau fournisseur hébergé, cliquez sur **Nouveau**, puis sur **Fournisseur hébergé**.</span><span class="sxs-lookup"><span data-stu-id="e9216-112">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="e9216-113">Si vous devez modifier une entrée dans la liste des fournisseurs hébergés, sélectionnez un fournisseur hébergé, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="e9216-113">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="e9216-114">Dans la page **Modifier le fournisseur fédéré SIP**, vous pouvez taper ou modifier les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="e9216-114">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="e9216-115">**Activer les communications avec ce fournisseur**     La sélection de ce paramètre active les communications avec les utilisateurs de ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e9216-115">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="e9216-116">**Nom du fournisseur :**     Une propriété obligatoire, tapez le nom du fournisseur tel qu’il apparaîtra dans la liste des fournisseurs fédérés SIP.</span><span class="sxs-lookup"><span data-stu-id="e9216-116">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="e9216-117">**Service Edge d’accès (FQDN) :**     Une propriété obligatoire, tapez le nom de domaine complet du service Edge d’accès du fournisseur hébergé que vous configurez.</span><span class="sxs-lookup"><span data-stu-id="e9216-117">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="e9216-118">Cette information doit être fournie par le fournisseur hébergée et ne doit être modifiée que si le fournisseur hébergé modifie le nom de domaine complet de son service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="e9216-118">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="e9216-119">**Niveau de vérification par défaut :**     Le paramètre par défaut, **autoriser les utilisateurs à communiquer avec des personnes de leur liste de contacts qui utilisent ce fournisseur** , limite la communication aux contacts que vous avez acceptés et se trouve dans votre liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="e9216-119">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="e9216-p103">Sélectionnez **Autoriser les utilisateurs à communiquer avec toutes les personnes qui utilisent ce fournisseur** pour supprimer la restriction sur la réception et l’acceptation d’invitations de contacts. Ce paramètre n’applique aucune restriction sur les personnes qui peuvent vous contacter à partir du réseau du fournisseur hébergé.</span><span class="sxs-lookup"><span data-stu-id="e9216-p103">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="e9216-122">Une fois que vous avez configuré les paramètres, cliquez sur **Valider** pour les enregistrer ou sur **Annuler** pour annuler vos modifications.</span><span class="sxs-lookup"><span data-stu-id="e9216-122">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e9216-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e9216-123">See Also</span></span>


[<span data-ttu-id="e9216-124">Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9216-124">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="e9216-125">Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9216-125">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

