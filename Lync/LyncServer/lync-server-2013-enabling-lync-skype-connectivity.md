---
title: 'Lync Server 2013 : activation de la connectivité Lync-Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 794d2a71c07e742a3ab5597d4bd2aff77157d675
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="1ffc3-102">Activation de la connectivité Lync-Skype dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ffc3-102">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ffc3-103">_**Dernière modification de la rubrique:** 2014-12-16_</span><span class="sxs-lookup"><span data-stu-id="1ffc3-103">_**Topic Last Modified:** 2014-12-16_</span></span>

<span data-ttu-id="1ffc3-104">Après avoir soumis la demande de mise en service, vous pouvez vous concentrer sur l’environnement du serveur Lync et les tâches d’administration requises pour configurer Lync-connectivité Skype.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-104">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="1ffc3-105">Dans cette section, nous supposons que l’administrateur du serveur Lync a déployé Lync Server et configuré l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-105">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="1ffc3-106">Pour plus d’informations sur la configuration de l’accès externe pour Lync Server, reportez-vous à la rubrique [planification de l’accès des utilisateurs externes dans Lync server 2013](lync-server-2013-planning-for-external-user-access.md) et [déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="1ffc3-106">For additional information on configuring external access for Lync Server, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

<span data-ttu-id="1ffc3-107">Pour préparer l’environnement Lync Server pour Lync-connectivité Skype, l’administrateur du serveur Lync doit effectuer les trois tâches suivantes:</span><span class="sxs-lookup"><span data-stu-id="1ffc3-107">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="1ffc3-108">1 \.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-108">1\.</span></span> <span data-ttu-id="1ffc3-109">Configurer la fédération et PIC</span><span class="sxs-lookup"><span data-stu-id="1ffc3-109">Configure Federation and PIC</span></span>

<span data-ttu-id="1ffc3-110">La Fédération est requise pour permettre aux utilisateurs de Skype de communiquer avec les utilisateurs de Lync au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-110">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="1ffc3-111">La connectivité de messagerie instantanée publique (PIC) est une classe de Fédération qui doit être configurée pour permettre aux utilisateurs de Lync de communiquer avec des utilisateurs Skype.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-111">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="1ffc3-112">Les options de Fédération et PIC sont configurées à l’aide du panneau de configuration de Lync Server, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-112">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<span data-ttu-id="1ffc3-113">![Affichage] de la photo (images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Affichage") de la photo</span><span class="sxs-lookup"><span data-stu-id="1ffc3-113">![Showing PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Showing PIC")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1ffc3-114">La fédération PIC n’est plus prise en charge par Live Communication Server 2005 SP1 ni par Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-114">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="1ffc3-115">Les plateformes prises en charge pour la Fédération PIC incluent Lync Server 2013, Lync Server 2010 et Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-115">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="1ffc3-116">2 \.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-116">2\.</span></span> <span data-ttu-id="1ffc3-117">Configurer au moins une stratégie pour la prise en charge de l’accès des utilisateurs fédérés</span><span class="sxs-lookup"><span data-stu-id="1ffc3-117">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="1ffc3-118">À l’aide du panneau de configuration de Lync Server, un administrateur doit configurer une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs de Skype peuvent collaborer avec des utilisateurs internes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-118">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

<span data-ttu-id="1ffc3-119">![Politiques] (images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Politiques")</span><span class="sxs-lookup"><span data-stu-id="1ffc3-119">![Policies](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Policies")</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="1ffc3-120">3 \.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-120">3\.</span></span> <span data-ttu-id="1ffc3-121">Configuration du paramètre du fournisseur de PIC Skype pour Lync</span><span class="sxs-lookup"><span data-stu-id="1ffc3-121">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="1ffc3-122">À l’aide de Lync Server Management Shell, un administrateur doit configurer la stratégie de client Lync pour afficher Skype en tant que fournisseur de PIC supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-122">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ffc3-123">Les utilisateurs des fournisseurs de service de messagerie instantanée publique ne peuvent pas participer à des conférences par messagerie instantanée ou audio ou vidéo dans votre organisation tant que vous n’avez pas configuré au moins une stratégie (étape 2, plus haut dans cette procédure) pour prendre en charge la connectivité de messagerie instantanée publique.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-123">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or audio or video conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span>



</div>

1.  <span data-ttu-id="1ffc3-124">Pour configurer la Fédération et la messagerie instantanée, voir Activer ou désactiver la Fédération et la connectivité [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063)de messagerie instantanée publique à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-124">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063).</span></span>

2.  <span data-ttu-id="1ffc3-125">Pour configurer au moins une stratégie pour la prise en charge de l’accès des utilisateurs fédérés, voir «Configurer des stratégies [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064)pour contrôler l’accès public aux utilisateurs».</span><span class="sxs-lookup"><span data-stu-id="1ffc3-125">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064).</span></span>

<span data-ttu-id="1ffc3-126">**Pour modifier un fournisseur de services de messagerie instantanée ou Skype existant et le configurer pour Skype**</span><span class="sxs-lookup"><span data-stu-id="1ffc3-126">**To edit an existing Messenger or Skype PIC provider and configure it for Skype**</span></span>

1.  <span data-ttu-id="1ffc3-127">À partir d’un serveur frontal Lync Server, ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-127">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="1ffc3-128">Exécutez les deux commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="1ffc3-128">Run the following two commands:</span></span>
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1ffc3-129">Si vous n’avez pas encore de fournisseur PIC dans votre environnement et que vous êtes en train de créer un nouveau fournisseur de PIC, vous n’avez pas besoin d’exécuter l’applet de action <STRONG>Remove-CsPublicProvider</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="1ffc3-129">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1ffc3-130">Ajouté dans Lync Server 2013 CU5 &amp; le client de bureau Lync dans Office 2013 SP1, le NameDecorationRoutingDomain et NameDecorationExcludedDomainList d’améliorer la situation dans laquelle les utilisateurs de Lync ajoutent des contacts Skype nécessaires pour «décorer» des domaines non Microsoft vers Identifiez-les et acheminez-les vers Skype (format: utilisateur (contoso. com) @msn. com).</span><span class="sxs-lookup"><span data-stu-id="1ffc3-130">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="1ffc3-131">Ces nouveaux paramètres permettent la mise en forme automatique de l’adresse que l’utilisateur entre dans la boîte de dialogue « Ajouter un contact Skype » avec NameDecorationRoutingDomain (qui doit être défini sur msn.com) si elle ne contient pas les domaines dans NameDecorationExcludedDomainList (actuellement, nous pouvons prendre en charge msn.com, live.com, Hotmail.com et outlook.com).</span><span class="sxs-lookup"><span data-stu-id="1ffc3-131">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

    
    </div>

3.  <span data-ttu-id="1ffc3-132">À partir d’un client Lync, vous pouvez désormais sélectionner Skype en tant que fournisseur de PIC et ajouter un client Skype en spécifiant son compte Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-132">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="1ffc3-133">De plus, un utilisateur de Skype qui a fusionné et connecté avec son compte Microsoft peut envoyer une demande de contact à des utilisateurs de Lync.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-133">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="1ffc3-134">Pour plus d’informations sur les comptes Microsoft, voir [qu’est-ce qu’un compte Microsoft?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span><span class="sxs-lookup"><span data-stu-id="1ffc3-134">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="1ffc3-135">Pour plus d’informations sur l’ajout de clients à Lync, reportez-vous à la rubrique [utilisation de Lync-connectivité Skype dans Lync Server 2013 en tant qu’utilisateur final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span><span class="sxs-lookup"><span data-stu-id="1ffc3-135">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>
    
    <span data-ttu-id="1ffc3-136">![Ajouter un contact Skype] (images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Ajouter un contact Skype")</span><span class="sxs-lookup"><span data-stu-id="1ffc3-136">![Add Skype Contact](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Add Skype Contact")</span></span>

4.  <span data-ttu-id="1ffc3-137">Pour plus d’informations sur la modification des fournisseurs hébergés, voir «créer ou modifier des fournisseurs fédérés [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065)SIP hébergés» à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-137">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="1ffc3-138">Cette procédure termine les tâches d’administration qui doivent être effectuées sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-138">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="1ffc3-139">Vous êtes désormais configuré pour Lync-connectivité Skype.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-139">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

