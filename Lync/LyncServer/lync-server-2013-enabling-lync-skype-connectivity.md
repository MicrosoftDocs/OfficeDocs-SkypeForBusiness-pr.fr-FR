---
title: 'Lync Server 2013 : activation de la connectivité Lync-Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43e26e54d0704ed009af1ef528e60979b759eb69
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528581"
---
# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="18b67-102">Activation de la connectivité Lync-Skype dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18b67-102">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18b67-103">_**Dernière modification de la rubrique :** 2014-12-16_</span><span class="sxs-lookup"><span data-stu-id="18b67-103">_**Topic Last Modified:** 2014-12-16_</span></span>

<span data-ttu-id="18b67-104">Une fois que vous avez soumis la demande de mise en service, vous pouvez vous concentrer sur l’environnement Lync Server et les tâches administratives requises pour configurer la connectivité Lync-Skype.</span><span class="sxs-lookup"><span data-stu-id="18b67-104">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="18b67-105">Dans cette section, nous partons du principe que l’administrateur Lync Server a déployé Lync Server et configuré l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="18b67-105">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="18b67-106">Pour plus d’informations sur la configuration de l’accès externe pour Lync Server, consultez la rubrique [planification de l’accès des utilisateurs externes dans Lync server 2013](lync-server-2013-planning-for-external-user-access.md) et [déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="18b67-106">For additional information on configuring external access for Lync Server, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

<span data-ttu-id="18b67-107">Pour préparer l’environnement Lync Server pour la connectivité Lync-Skype, l’administrateur Lync Server doit effectuer les trois tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="18b67-107">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="18b67-108">1\.</span><span class="sxs-lookup"><span data-stu-id="18b67-108">1\.</span></span> <span data-ttu-id="18b67-109">Configuration de la Fédération et de PIC</span><span class="sxs-lookup"><span data-stu-id="18b67-109">Configure Federation and PIC</span></span>

<span data-ttu-id="18b67-110">La Fédération est nécessaire pour permettre aux utilisateurs de Skype de communiquer avec des utilisateurs de Lync dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="18b67-110">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="18b67-111">La connectivité PIC (public Instant Messaging Connectivity) est une classe de Fédération et elle doit être configurée pour permettre à vos utilisateurs Lync de communiquer avec des utilisateurs de Skype.</span><span class="sxs-lookup"><span data-stu-id="18b67-111">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="18b67-112">La Fédération et PIC sont configurés à l’aide du panneau de configuration Lync Server, comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="18b67-112">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<span data-ttu-id="18b67-113">![Affichage de PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Affichage de PIC")</span><span class="sxs-lookup"><span data-stu-id="18b67-113">![Showing PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Showing PIC")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="18b67-114">La Fédération PIC n’est plus prise en charge par Live Communication Server 2005 SP1 ou par Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18b67-114">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="18b67-115">Les plateformes prises en charge pour la Fédération PIC incluent Lync Server 2013, Lync Server 2010 et Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18b67-115">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="18b67-116">2\.</span><span class="sxs-lookup"><span data-stu-id="18b67-116">2\.</span></span> <span data-ttu-id="18b67-117">Configurer au moins une stratégie pour prendre en charge l’accès des utilisateurs fédérés</span><span class="sxs-lookup"><span data-stu-id="18b67-117">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="18b67-118">À l’aide du panneau de configuration Lync Server, un administrateur doit configurer une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs de Skype peuvent collaborer avec des utilisateurs internes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18b67-118">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

<span data-ttu-id="18b67-119">![Stratégies](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Stratégies")</span><span class="sxs-lookup"><span data-stu-id="18b67-119">![Policies](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Policies")</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="18b67-120">3\.</span><span class="sxs-lookup"><span data-stu-id="18b67-120">3\.</span></span> <span data-ttu-id="18b67-121">Configurer le paramètre de fournisseur PIC Skype pour Lync</span><span class="sxs-lookup"><span data-stu-id="18b67-121">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="18b67-122">À l’aide de Lync Server Management Shell, un administrateur doit configurer la stratégie de client Lync pour qu’elle affiche Skype en tant que fournisseur PIC supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="18b67-122">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18b67-123">Les utilisateurs des fournisseurs de services PIC (public Instant Messaging Connectivity) ne peuvent pas participer à des conférences de messagerie instantanée, audio ou vidéo dans votre organisation tant que vous ne configurez pas au moins une stratégie (étape 2, plus haut dans cette procédure), pour prendre en charge la connectivité PIC.</span><span class="sxs-lookup"><span data-stu-id="18b67-123">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or audio or video conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span>



</div>

1.  <span data-ttu-id="18b67-124">Pour configurer la Fédération et PIC, voir « Activer ou désactiver la Fédération et la connectivité PIC » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=306063](https://go.microsoft.com/fwlink/p/?linkid=306063) .</span><span class="sxs-lookup"><span data-stu-id="18b67-124">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at [https://go.microsoft.com/fwlink/p/?LinkId=306063](https://go.microsoft.com/fwlink/p/?linkid=306063).</span></span>

2.  <span data-ttu-id="18b67-125">Pour configurer au moins une stratégie pour prendre en charge l’accès des utilisateurs fédérés, voir « Configurer des stratégies pour contrôler l’accès des utilisateurs publics » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=306064](https://go.microsoft.com/fwlink/p/?linkid=306064) .</span><span class="sxs-lookup"><span data-stu-id="18b67-125">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at [https://go.microsoft.com/fwlink/p/?LinkId=306064](https://go.microsoft.com/fwlink/p/?linkid=306064).</span></span>

<span data-ttu-id="18b67-126">**Pour modifier un fournisseur de messagerie instantanée Messenger ou Skype existant et le configurer pour Skype**</span><span class="sxs-lookup"><span data-stu-id="18b67-126">**To edit an existing Messenger or Skype PIC provider and configure it for Skype**</span></span>

1.  <span data-ttu-id="18b67-127">À partir d’un serveur frontal Lync Server, ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="18b67-127">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="18b67-128">Exécutez les deux commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="18b67-128">Run the following two commands:</span></span>
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="18b67-129">Si vous n’avez pas encore de fournisseur PIC dans votre environnement et que vous créez un nouveau fournisseur PIC, vous n’avez pas besoin d’exécuter la cmdlet <STRONG>Remove-applet cspublicprovider</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="18b67-129">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="18b67-130">Ajouté dans Lync Server 2013 CU5 &amp; client Lync dans Office 2013 SP1, le NameDecorationRoutingDomain et NameDecorationExcludedDomainList améliorent la situation dans laquelle les utilisateurs de Lync ajoutent des contacts Skype nécessaires pour « décorer » des domaines non-Microsoft afin de les identifier et de les acheminer vers Skype (format de : User (contoso. com) @msn. com).</span><span class="sxs-lookup"><span data-stu-id="18b67-130">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="18b67-131">Ces nouveaux paramètres autorisent la mise en forme automatique de l’adresse entrée de l’utilisateur dans la boîte de dialogue « Ajouter un contact Skype » avec le NameDecorationRoutingDomain (qui doit être défini sur msn.com) s’il ne contient pas les domaines dans le NameDecorationExcludedDomainList (nous pouvons actuellement prendre en charge msn.com, live.com, Hotmail.com, outlook.com).</span><span class="sxs-lookup"><span data-stu-id="18b67-131">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

    
    </div>

3.  <span data-ttu-id="18b67-132">À partir d’un client Lync, vous pouvez désormais sélectionner Skype comme fournisseur PIC et ajouter un client Skype en spécifiant son compte Microsoft.</span><span class="sxs-lookup"><span data-stu-id="18b67-132">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="18b67-133">En outre, un utilisateur de Skype qui a fusionné et connecté avec son compte Microsoft peut envoyer une demande de contact aux utilisateurs de Lync.</span><span class="sxs-lookup"><span data-stu-id="18b67-133">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="18b67-134">Pour plus d’informations sur les comptes Microsoft, consultez [qu’est-ce qu’un compte Microsoft ?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span><span class="sxs-lookup"><span data-stu-id="18b67-134">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="18b67-135">Pour plus d’informations sur l’ajout de clients à Lync, voir [Using Lync-Skype Connectivity in Lync Server 2013 as an End User](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span><span class="sxs-lookup"><span data-stu-id="18b67-135">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>
    
    <span data-ttu-id="18b67-136">![Ajouter un contact Skype](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Ajouter un contact Skype")</span><span class="sxs-lookup"><span data-stu-id="18b67-136">![Add Skype Contact](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Add Skype Contact")</span></span>

4.  <span data-ttu-id="18b67-137">Pour plus d’informations sur la modification des fournisseurs hébergés, consultez la rubrique « créer ou modifier des fournisseurs fédérés SIP hébergés » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065) .</span><span class="sxs-lookup"><span data-stu-id="18b67-137">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="18b67-138">Cette opération termine les tâches d’administration qui doivent être effectuées sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="18b67-138">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="18b67-139">Vous êtes maintenant configuré pour la connectivité Lync-Skype.</span><span class="sxs-lookup"><span data-stu-id="18b67-139">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

