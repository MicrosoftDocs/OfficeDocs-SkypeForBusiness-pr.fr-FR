---
title: Accès au site de mise en service de la connectivité PIC de Lync Server
description: Accès au site de mise en service de la connectivité PIC (Public IM Connectivity) de Lync Server.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e12916b12de1ef3a3f990c6bee54c312ba6c1992
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571130"
---
# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a><span data-ttu-id="fc0d9-103">Accès au site de mise en service de la connectivité PIC (Public IM Connectivity) de Lync Server à partir de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc0d9-103">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc0d9-104">_**Dernière modification de la rubrique :** 2019-03-22_</span><span class="sxs-lookup"><span data-stu-id="fc0d9-104">_**Topic Last Modified:** 2019-03-22_</span></span>

<span data-ttu-id="fc0d9-105">Le processus de mise en service pour la connectivité Lync-Skype a changé, par rapport aux méthodes de mise en service PIC précédentes.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-105">The provisioning process for Lync-Skype connectivity has changed, as compared to previous PIC provisioning methods.</span></span> <span data-ttu-id="fc0d9-106">Le processus de mise en service peut prendre jusqu’à 30 jours.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-106">This provisioning process can take up to thirty days to complete.</span></span> <span data-ttu-id="fc0d9-107">Nous vous recommandons de commencer par démarrer ce processus avant d’effectuer les étapes restantes dans ce document.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-107">We recommend that you start this process first, prior to completing the remaining steps in this document.</span></span> <span data-ttu-id="fc0d9-108">Une fois le processus de mise en service de Lync-Skype terminé pour votre compte, le compte est activé et vos utilisateurs éligibles sont activés pour la connectivité PIC.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-108">After the Lync-Skype provisioning process is completed for your account, the account is activated and your eligible users are enabled for public IM connectivity.</span></span>

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a><span data-ttu-id="fc0d9-109">Pour mettre en service la connectivité Lync-Skype, vous avez besoin des informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="fc0d9-109">To provision Lync-Skype connectivity, you need the following information:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="fc0d9-110">Numéro de contrat Microsoft</span><span class="sxs-lookup"><span data-stu-id="fc0d9-110">Microsoft Agreement Number</span></span></p></li>
<li><p><span data-ttu-id="fc0d9-111">Nom de domaine complet (FQDN) du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="fc0d9-111">Access Edge service fully qualified domain name (FQDN)</span></span></p></li>
<li><p><span data-ttu-id="fc0d9-112">Domaine (s) SIP (Session Initiation Protocol)</span><span class="sxs-lookup"><span data-stu-id="fc0d9-112">Session Initiation Protocol (SIP) domain(s)</span></span></p></li>
<li><p><span data-ttu-id="fc0d9-113">Tous les noms de domaine complets du service Edge d’accès supplémentaires</span><span class="sxs-lookup"><span data-stu-id="fc0d9-113">Any additional Access Edge service FQDNs</span></span></p></li>
<li><p><span data-ttu-id="fc0d9-114">Informations de contact</span><span class="sxs-lookup"><span data-stu-id="fc0d9-114">Contact information</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fc0d9-115">À compter du 2019 avril, nous allons arrêter la collecte et la rétention des informations de contact pour les clients qui sont configurés pour la Fédération Skype via le site Web pic.lync.com.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-115">Beginning in April 2019, we will stop the collection and retention of contact information for customers who are provisioned for Skype Federation via the pic.lync.com website.</span></span> <span data-ttu-id="fc0d9-116">Cette modification est effectuée afin de s’assurer que le système de mise en service pic.lync.com adhère aux stratégies de confidentialité de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-116">This change is being made to ensure that the pic.lync.com provisioning system adheres to Microsoft privacy policies.</span></span> 

<span data-ttu-id="fc0d9-117">Une fois que cette modification a lieu, nous ne pourrons plus fournir de mises à jour de messagerie sur les modifications de mise en service en attente.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-117">Once this change goes live, we will no longer be able to provide email updates on pending provisioning changes.</span></span> <span data-ttu-id="fc0d9-118">Les modifications de mise en service PIC se terminent généralement dans les 24-48 heures après leur entrée.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-118">PIC provisioning changes typically complete within 24-48 hours after being entered.</span></span> <span data-ttu-id="fc0d9-119">Si vous rencontrez toujours des problèmes de Fédération Skype 48 heures après avoir soumis une demande de mise en service, contactez le support technique Microsoft pour en savoir plus.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-119">If you are still experiencing Skype Federation issues 48 hours after submitting a provisioning request, please engage Microsoft Technical Support to investigate further.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc0d9-120">Dans le cadre de cette modification, toutes les informations de contact précédemment entrées seront purgées de notre système à la fin du 2019 avril.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-120">As part of this change, all previously entered contact information will be purged from our system by the end of April, 2019.</span></span>

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a><span data-ttu-id="fc0d9-121">Pour lancer le processus de mise en service pour la connectivité Lync-Skype :</span><span class="sxs-lookup"><span data-stu-id="fc0d9-121">To initiate the provisioning process for Lync-Skype connectivity:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="fc0d9-122">Connectez-vous au site Web, <strong>https://pic.lync.com</strong> à l’aide de votre identifiant Microsoft Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-122">Sign in to the website, <strong>https://pic.lync.com</strong>, using your Microsoft Windows Live ID.</span></span></p></li>
<li><p><span data-ttu-id="fc0d9-123">Sélectionnez le type de contrat de licence Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-123">Select the Microsoft licensing agreement type.</span></span></p></li>
<li><p><span data-ttu-id="fc0d9-124">Activez la case à cocher, en vérifiant que vous avez lu et accepté les droits d’utilisation du produit pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-124">Select the check box, verifying that you have read and accept the Product Use Rights for Lync Server.</span></span></p></li>
<li><p><span data-ttu-id="fc0d9-125">Dans la page <strong>lancer une demande de mise en service</strong> , cliquez sur le lien approprié pour lancer une demande de mise en service :</span><span class="sxs-lookup"><span data-stu-id="fc0d9-125">On the <strong>Initiate a Provisioning Request</strong> page, click the appropriate link to initiate a provisioning request:</span></span></p></li>
<li><p><span data-ttu-id="fc0d9-126">Sur la page <strong>spécifier les informations de mise en service</strong> , entrez le nom de <strong>domaine complet du service Edge d’accès</strong>.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-126">On the <strong>Specify Provisioning Information</strong> page, enter the <strong>Access Edge service FQDN</strong>.</span></span> <span data-ttu-id="fc0d9-127">Par exemple, <strong>SIP.contoso.com</strong>.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-127">For example, <strong>sip.contoso.com</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="fc0d9-128">Après le 1er juillet, 2017 Microsoft aura également besoin que l’enregistrement DNS SRV de Fédération déployé pour la connectivité PIC pour continuer à fonctionner.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-128">After July 1st, 2017 Microsoft will additionally require customers have the Federation DNS SRV record deployed for Public IM connectivity to continue to work.</span></span>

</li>
<li><p><span data-ttu-id="fc0d9-129">Entrez au moins un ou plusieurs noms de domaine SIP, puis cliquez sur <strong>Ajouter</strong>.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-129">Enter at least one or more SIP domain names, and then click <strong>Add</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="fc0d9-130">Au moins un serveur Edge d’accès et un domaine SIP sont requis pour terminer le processus de mise en service.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-130">At least one Access Edge server and one SIP domain are required to complete the provisioning process.</span></span> <span data-ttu-id="fc0d9-131">Le domaine SIP et le serveur Edge d’accès doivent être actifs, opérationnels et accessibles sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-131">The SIP domain and the Access Edge server must be active, functioning, and reachable on the network.</span></span>

</li>
<li><p><span data-ttu-id="fc0d9-132">Dans la liste des <strong>fournisseurs de services de messagerie instantanée publics</strong>, sélectionnez <strong>Skype,</strong> puis cliquez sur <strong>suivant</strong> pour ajouter des informations de contact, puis envoyez la demande de mise en service.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-132">In the list of <strong>Public IM Service providers</strong>, select <strong>Skype,</strong> and click <strong>Next</strong> to add contact information, and submit the provisioning request.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fc0d9-133">Une fois la demande de mise en service envoyée, il peut falloir jusqu’à 30 jours pour l’activation du compte et pour que les utilisateurs soient activés pour la connectivité PIC.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-133">After the provisioning request has been submitted, it can take up to 30 days for the account to activate and for users to be enabled for public IM connectivity.</span></span>

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a><span data-ttu-id="fc0d9-134">Activation de la Fédération et de la connectivité PIC (Public IM Connectivity)</span><span class="sxs-lookup"><span data-stu-id="fc0d9-134">Enabling Federation and Public IM Connectivity (PIC)</span></span>

<span data-ttu-id="fc0d9-135">Une fois que vous avez soumis la demande de mise en service, vous pouvez vous concentrer sur l’environnement Lync Server et les tâches administratives requises pour configurer la connectivité Lync-Skype.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-135">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="fc0d9-136">Dans cette section, nous partons du principe que l’administrateur Lync Server a déployé Lync Server et configuré l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-136">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="fc0d9-137">Pour plus d’informations sur la configuration de l’accès externe pour Lync Server, voir « Planification de l’accès des utilisateurs externes » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) et « déploiement de l’accès des utilisateurs externes » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378) .</span><span class="sxs-lookup"><span data-stu-id="fc0d9-137">For additional information on configuring external access for Lync Server, see "Planning for External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) and "Deploying External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378).</span></span>

<span data-ttu-id="fc0d9-138">Pour préparer l’environnement Lync Server pour la connectivité Lync-Skype, l’administrateur Lync Server doit effectuer les trois tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="fc0d9-138">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="fc0d9-139">1\.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-139">1\.</span></span> <span data-ttu-id="fc0d9-140">Configuration de la Fédération et de PIC</span><span class="sxs-lookup"><span data-stu-id="fc0d9-140">Configure Federation and PIC</span></span>

<span data-ttu-id="fc0d9-141">La Fédération est nécessaire pour permettre aux utilisateurs de Skype de communiquer avec des utilisateurs de Lync dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-141">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="fc0d9-142">La connectivité PIC (public Instant Messaging Connectivity) est une classe de Fédération et elle doit être configurée pour permettre à vos utilisateurs Lync de communiquer avec des utilisateurs de Skype.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-142">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="fc0d9-143">La Fédération et PIC sont configurés à l’aide du panneau de configuration Lync Server, comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-143">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="fc0d9-144">La Fédération PIC n’est plus prise en charge par Live Communication Server 2005 SP1 ou par Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-144">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="fc0d9-145">Les plateformes prises en charge pour la Fédération PIC incluent Lync Server 2013, Lync Server 2010 et Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-145">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="fc0d9-146">2\.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-146">2\.</span></span> <span data-ttu-id="fc0d9-147">Configurer au moins une stratégie pour prendre en charge l’accès des utilisateurs fédérés</span><span class="sxs-lookup"><span data-stu-id="fc0d9-147">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="fc0d9-148">À l’aide du panneau de configuration Lync Server, un administrateur doit configurer une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs de Skype peuvent collaborer avec des utilisateurs internes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-148">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="fc0d9-149">3\.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-149">3\.</span></span> <span data-ttu-id="fc0d9-150">Configurer le paramètre de fournisseur PIC Skype pour Lync</span><span class="sxs-lookup"><span data-stu-id="fc0d9-150">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="fc0d9-151">À l’aide de Lync Server Management Shell, un administrateur doit configurer la stratégie de client Lync pour qu’elle affiche Skype en tant que fournisseur PIC supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-151">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="fc0d9-152">Les utilisateurs des fournisseurs de services PIC (public Instant Messaging Connectivity) ne peuvent pas participer à la messagerie instantanée ou aux conférences de votre organisation tant que vous ne configurez pas au moins une stratégie (étape 2, plus haut dans cette procédure), pour prendre en charge la connectivité PIC.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-152">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span><BR><span data-ttu-id="fc0d9-153">Pour configurer la Fédération et PIC, voir « Activer ou désactiver la Fédération et la connectivité PIC » à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A> .</span><span class="sxs-lookup"><span data-stu-id="fc0d9-153">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>.</span></span><BR><span data-ttu-id="fc0d9-154">Pour configurer au moins une stratégie pour prendre en charge l’accès des utilisateurs fédérés, voir « Configurer des stratégies pour contrôler l’accès des utilisateurs publics » à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A> .</span><span class="sxs-lookup"><span data-stu-id="fc0d9-154">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>.</span></span>



</div>

1.  <span data-ttu-id="fc0d9-155">À partir d’un serveur frontal Lync Server, ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-155">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="fc0d9-156">Exécutez les deux commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="fc0d9-156">Run the following two commands:</span></span>
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="fc0d9-157">Si vous n’avez pas encore de fournisseur PIC dans votre environnement et que vous créez un nouveau fournisseur PIC, vous n’avez pas besoin d’exécuter la cmdlet <STRONG>Remove-applet cspublicprovider</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="fc0d9-157">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="fc0d9-158">Ajouté dans Lync Server 2013 CU5 &amp; client Lync dans Office 2013 SP1, le NameDecorationRoutingDomain et NameDecorationExcludedDomainList améliorent la situation dans laquelle les utilisateurs de Lync ajoutent des contacts Skype nécessaires pour « décorer » des domaines non-Microsoft afin de les identifier et de les acheminer vers Skype (format de : User (contoso. com) @msn. com).</span><span class="sxs-lookup"><span data-stu-id="fc0d9-158">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="fc0d9-159">Ces nouveaux paramètres autorisent la mise en forme automatique de l’adresse entrée de l’utilisateur dans la boîte de dialogue « Ajouter un contact Skype » avec le NameDecorationRoutingDomain (qui doit être défini sur msn.com) s’il ne contient pas les domaines dans le NameDecorationExcludedDomainList (nous pouvons actuellement prendre en charge msn.com, live.com, Hotmail.com, outlook.com).</span><span class="sxs-lookup"><span data-stu-id="fc0d9-159">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

        
        </div>

3.  <span data-ttu-id="fc0d9-160">À partir d’un client Lync, vous pouvez désormais sélectionner Skype comme fournisseur PIC et ajouter un client Skype en spécifiant son compte Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-160">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="fc0d9-161">En outre, un utilisateur de Skype qui a fusionné et connecté avec son compte Microsoft peut envoyer une demande de contact aux utilisateurs de Lync.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-161">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="fc0d9-162">Pour plus d’informations sur les comptes Microsoft, consultez [qu’est-ce qu’un compte Microsoft ?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span><span class="sxs-lookup"><span data-stu-id="fc0d9-162">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="fc0d9-163">Pour plus d’informations sur l’ajout de clients à Lync, voir [Using Lync-Skype Connectivity in Lync Server 2013 as an End User](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span><span class="sxs-lookup"><span data-stu-id="fc0d9-163">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>

4.  <span data-ttu-id="fc0d9-164">Pour plus d’informations sur la modification des fournisseurs hébergés, consultez la rubrique « créer ou modifier des fournisseurs fédérés SIP hébergés » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065) .</span><span class="sxs-lookup"><span data-stu-id="fc0d9-164">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="fc0d9-165">Cette opération termine les tâches d’administration qui doivent être effectuées sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-165">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="fc0d9-166">Vous êtes maintenant configuré pour la connectivité Lync-Skype.</span><span class="sxs-lookup"><span data-stu-id="fc0d9-166">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<div>

## <a name="additional-resources"></a><span data-ttu-id="fc0d9-167">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="fc0d9-167">Additional Resources</span></span>

[<span data-ttu-id="fc0d9-168">Utilisation de la connectivité Lync-Skype dans Lync Server 2013 en tant qu’utilisateur final</span><span class="sxs-lookup"><span data-stu-id="fc0d9-168">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[<span data-ttu-id="fc0d9-169">Guide de mise en service pour la connectivité Lync-Skype dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc0d9-169">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

