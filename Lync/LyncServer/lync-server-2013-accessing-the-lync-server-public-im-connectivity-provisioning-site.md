---
title: Accès au site d’approvisionnement de connectivité PIC de Lync Server
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
ms.openlocfilehash: dbcb2e46380e7ed4bbd8499e83f638cb314844e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a><span data-ttu-id="0bf12-102">Accès au site d’approvisionnement de connectivité PIC de Lync Server à partir de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bf12-102">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bf12-103">_**Dernière modification de la rubrique :** 2019-03-22_</span><span class="sxs-lookup"><span data-stu-id="0bf12-103">_**Topic Last Modified:** 2019-03-22_</span></span>

<span data-ttu-id="0bf12-104">Le processus de mise en service de Lync-connectivité Skype a changé par rapport aux méthodes de mise en service de l’image précédente.</span><span class="sxs-lookup"><span data-stu-id="0bf12-104">The provisioning process for Lync-Skype connectivity has changed, as compared to previous PIC provisioning methods.</span></span> <span data-ttu-id="0bf12-105">Ce processus de mise en service peut durer jusqu’à trente jours.</span><span class="sxs-lookup"><span data-stu-id="0bf12-105">This provisioning process can take up to thirty days to complete.</span></span> <span data-ttu-id="0bf12-106">Nous vous recommandons de commencer par commencer ce processus avant d’effectuer les étapes restantes de ce document.</span><span class="sxs-lookup"><span data-stu-id="0bf12-106">We recommend that you start this process first, prior to completing the remaining steps in this document.</span></span> <span data-ttu-id="0bf12-107">Après l’exécution du processus de mise en service de Lync-Skype pour votre compte, le compte est activé et les utilisateurs éligibles sont activés pour la connectivité de messagerie instantanée publique.</span><span class="sxs-lookup"><span data-stu-id="0bf12-107">After the Lync-Skype provisioning process is completed for your account, the account is activated and your eligible users are enabled for public IM connectivity.</span></span>

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a><span data-ttu-id="0bf12-108">Pour configurer Lync-connectivité Skype, vous avez besoin des informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0bf12-108">To provision Lync-Skype connectivity, you need the following information:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="0bf12-109">Numéro de contrat Microsoft</span><span class="sxs-lookup"><span data-stu-id="0bf12-109">Microsoft Agreement Number</span></span></p></li>
<li><p><span data-ttu-id="0bf12-110">Nom de domaine complet (FQDN) du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="0bf12-110">Access Edge service fully qualified domain name (FQDN)</span></span></p></li>
<li><p><span data-ttu-id="0bf12-111">Domaine(s) SIP (Session Initiation Protocol)</span><span class="sxs-lookup"><span data-stu-id="0bf12-111">Session Initiation Protocol (SIP) domain(s)</span></span></p></li>
<li><p><span data-ttu-id="0bf12-112">Noms complets (FQDN) supplémentaires éventuels du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="0bf12-112">Any additional Access Edge service FQDNs</span></span></p></li>
<li><p><span data-ttu-id="0bf12-113">Coordonnées</span><span class="sxs-lookup"><span data-stu-id="0bf12-113">Contact information</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>

<span data-ttu-id="0bf12-114">À compter du 2019 avril, nous mettrons fin à la collecte et la conservation des informations de contact des clients approvisionnés par Skype Federation par le biais du site Web pic.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0bf12-114">Beginning in April 2019, we will stop the collection and retention of contact information for customers who are provisioned for Skype Federation via the pic.lync.com website.</span></span> <span data-ttu-id="0bf12-115">Cette modification est apportée pour s’assurer que le système de mise en service de pic.lync.com respecte les politiques de confidentialité de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0bf12-115">This change is being made to ensure that the pic.lync.com provisioning system adheres to Microsoft privacy policies.</span></span> 

<span data-ttu-id="0bf12-116">Lorsque le changement est en cours, nous ne pourrons plus fournir de mises à jour par e-mail sur les changements de mise en service en attente.</span><span class="sxs-lookup"><span data-stu-id="0bf12-116">Once this change goes live, we will no longer be able to provide email updates on pending provisioning changes.</span></span> <span data-ttu-id="0bf12-117">Les modifications apportées aux mises en service PIC s’effectuent généralement dans les 24-48 heures suivant la saisie.</span><span class="sxs-lookup"><span data-stu-id="0bf12-117">PIC provisioning changes typically complete within 24-48 hours after being entered.</span></span> <span data-ttu-id="0bf12-118">Si vous continuez à rencontrer des problèmes avec la Fédération de Skype 48 heures après avoir envoyé une demande de provisionnement, contactez le support technique de Microsoft pour approfondir votre investigation.</span><span class="sxs-lookup"><span data-stu-id="0bf12-118">If you are still experiencing Skype Federation issues 48 hours after submitting a provisioning request, please engage Microsoft Technical Support to investigate further.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0bf12-119">Dans le cadre de cette modification, toutes les informations de contact précédemment entrées sont purgées de notre système à la fin du 1er avril 2019.</span><span class="sxs-lookup"><span data-stu-id="0bf12-119">As part of this change, all previously entered contact information will be purged from our system by the end of April, 2019.</span></span>

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a><span data-ttu-id="0bf12-120">Pour démarrer le processus de mise en service de Lync-connectivité Skype :</span><span class="sxs-lookup"><span data-stu-id="0bf12-120">To initiate the provisioning process for Lync-Skype connectivity:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="0bf12-121">Connectez-vous au site Web <strong>https://pic.lync.com</strong>, à l’aide de votre identifiant Microsoft Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="0bf12-121">Sign in to the website, <strong>https://pic.lync.com</strong>, using your Microsoft Windows Live ID.</span></span></p></li>
<li><p><span data-ttu-id="0bf12-122">Sélectionnez le type de contrat de licence Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0bf12-122">Select the Microsoft licensing agreement type.</span></span></p></li>
<li><p><span data-ttu-id="0bf12-123">Activez cette case à cocher pour vérifier que vous avez lu et accepté les droits d’utilisation du produit sur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0bf12-123">Select the check box, verifying that you have read and accept the Product Use Rights for Lync Server.</span></span></p></li>
<li><p><span data-ttu-id="0bf12-124">Dans la page <strong>initier une demande de mise en service</strong> , cliquez sur le lien approprié pour lancer une demande de configuration :</span><span class="sxs-lookup"><span data-stu-id="0bf12-124">On the <strong>Initiate a Provisioning Request</strong> page, click the appropriate link to initiate a provisioning request:</span></span></p></li>
<li><p><span data-ttu-id="0bf12-125">Dans la page <strong>spécifier les informations de mise en service</strong> , entrez le nom de <strong>domaine complet du service Edge d’accès</strong>.</span><span class="sxs-lookup"><span data-stu-id="0bf12-125">On the <strong>Specify Provisioning Information</strong> page, enter the <strong>Access Edge service FQDN</strong>.</span></span> <span data-ttu-id="0bf12-126">Par exemple, <strong>SIP.contoso.com</strong>.</span><span class="sxs-lookup"><span data-stu-id="0bf12-126">For example, <strong>sip.contoso.com</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="0bf12-127">Après le 1er juillet, 2017 Microsoft fera en sorte que le déploiement d’enregistrements SRV DNS de Fédération pour la connectivité de messagerie instantanée publique reste opérationnel pour les clients.</span><span class="sxs-lookup"><span data-stu-id="0bf12-127">After July 1st, 2017 Microsoft will additionally require customers have the Federation DNS SRV record deployed for Public IM connectivity to continue to work.</span></span>

</li>
<li><p><span data-ttu-id="0bf12-128">Entrez au moins un ou plusieurs noms de domaine SIP, puis cliquez sur <strong>Ajouter</strong>.</span><span class="sxs-lookup"><span data-stu-id="0bf12-128">Enter at least one or more SIP domain names, and then click <strong>Add</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="0bf12-129">Au moins un serveur Edge d’accès et un domaine SIP sont requis pour terminer le processus de mise en service.</span><span class="sxs-lookup"><span data-stu-id="0bf12-129">At least one Access Edge server and one SIP domain are required to complete the provisioning process.</span></span> <span data-ttu-id="0bf12-130">Le domaine SIP et le serveur Edge d’accès doivent être actifs, fonctionnels et accessibles sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="0bf12-130">The SIP domain and the Access Edge server must be active, functioning, and reachable on the network.</span></span>

</li>
<li><p><span data-ttu-id="0bf12-131">Dans la liste des <strong>fournisseurs de services de messagerie instantanée publique</strong>, sélectionnez <strong>Skype,</strong> cliquez sur <strong>suivant</strong> pour ajouter des informations de contact, puis envoyez la demande de mise en service.</span><span class="sxs-lookup"><span data-stu-id="0bf12-131">In the list of <strong>Public IM Service providers</strong>, select <strong>Skype,</strong> and click <strong>Next</strong> to add contact information, and submit the provisioning request.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0bf12-132">Après l’envoi de la demande de mise en service, l’activation du compte peut prendre jusqu’à 30 jours et permettre aux utilisateurs d’être activés pour la connectivité de messagerie instantanée publique.</span><span class="sxs-lookup"><span data-stu-id="0bf12-132">After the provisioning request has been submitted, it can take up to 30 days for the account to activate and for users to be enabled for public IM connectivity.</span></span>

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a><span data-ttu-id="0bf12-133">Activation de la fédération et de la connectivité PIC (Public IM Connectivity)</span><span class="sxs-lookup"><span data-stu-id="0bf12-133">Enabling Federation and Public IM Connectivity (PIC)</span></span>

<span data-ttu-id="0bf12-134">Après avoir soumis la demande de mise en service, vous pouvez vous concentrer sur l’environnement du serveur Lync et les tâches d’administration requises pour configurer Lync-connectivité Skype.</span><span class="sxs-lookup"><span data-stu-id="0bf12-134">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="0bf12-135">Dans cette section, nous supposons que l’administrateur du serveur Lync a déployé Lync Server et configuré l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="0bf12-135">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="0bf12-136">Pour plus d’informations sur la configuration de l’accès externe pour Lync Server, voir « planification pour l’accès [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) utilisateur externe » auprès de et « déploiement de [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378)l’accès utilisateur externe ».</span><span class="sxs-lookup"><span data-stu-id="0bf12-136">For additional information on configuring external access for Lync Server, see "Planning for External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) and "Deploying External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378).</span></span>

<span data-ttu-id="0bf12-137">Pour préparer l’environnement Lync Server pour Lync-connectivité Skype, l’administrateur du serveur Lync doit effectuer les trois tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="0bf12-137">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="0bf12-138">1 \.</span><span class="sxs-lookup"><span data-stu-id="0bf12-138">1\.</span></span> <span data-ttu-id="0bf12-139">Configurer la fédération et PIC</span><span class="sxs-lookup"><span data-stu-id="0bf12-139">Configure Federation and PIC</span></span>

<span data-ttu-id="0bf12-140">La Fédération est requise pour permettre aux utilisateurs de Skype de communiquer avec les utilisateurs de Lync au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0bf12-140">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="0bf12-141">La connectivité de messagerie instantanée publique (PIC) est une classe de Fédération qui doit être configurée pour permettre aux utilisateurs de Lync de communiquer avec des utilisateurs Skype.</span><span class="sxs-lookup"><span data-stu-id="0bf12-141">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="0bf12-142">Les options de Fédération et PIC sont configurées à l’aide du panneau de configuration de Lync Server, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="0bf12-142">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="0bf12-143">La fédération PIC n’est plus prise en charge par Live Communication Server 2005 SP1 ni par Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="0bf12-143">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="0bf12-144">Les plateformes prises en charge pour la Fédération PIC incluent Lync Server 2013, Lync Server 2010 et Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="0bf12-144">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="0bf12-145">2 \.</span><span class="sxs-lookup"><span data-stu-id="0bf12-145">2\.</span></span> <span data-ttu-id="0bf12-146">Configurer au moins une stratégie pour la prise en charge de l’accès des utilisateurs fédérés</span><span class="sxs-lookup"><span data-stu-id="0bf12-146">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="0bf12-147">À l’aide du panneau de configuration de Lync Server, un administrateur doit configurer une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs de Skype peuvent collaborer avec des utilisateurs internes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0bf12-147">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="0bf12-148">3 \.</span><span class="sxs-lookup"><span data-stu-id="0bf12-148">3\.</span></span> <span data-ttu-id="0bf12-149">Configuration du paramètre du fournisseur de PIC Skype pour Lync</span><span class="sxs-lookup"><span data-stu-id="0bf12-149">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="0bf12-150">À l’aide de Lync Server Management Shell, un administrateur doit configurer la stratégie de client Lync pour afficher Skype en tant que fournisseur de PIC supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="0bf12-150">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="0bf12-151">Les utilisateurs du service PIC ne peuvent pas participer à des sessions de messagerie instantanée ou des conférences dans votre organisation tant que vous n’avez pas configuré au moins une stratégie (étape 2 de cette procédure) pour prendre en charge la connectivité PIC. </span><span class="sxs-lookup"><span data-stu-id="0bf12-151">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span><BR><span data-ttu-id="0bf12-152">Pour configurer la Fédération et la messagerie instantanée, voir Activer ou désactiver la Fédération et la connectivité <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>de messagerie instantanée publique à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="0bf12-152">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>.</span></span><BR><span data-ttu-id="0bf12-153">Pour configurer au moins une stratégie pour la prise en charge de l’accès des utilisateurs fédérés, voir « Configurer des stratégies <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>pour contrôler l’accès public aux utilisateurs ».</span><span class="sxs-lookup"><span data-stu-id="0bf12-153">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>.</span></span>



</div>

1.  <span data-ttu-id="0bf12-154">À partir d’un serveur frontal Lync Server, ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0bf12-154">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="0bf12-155">Exécutez les deux commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="0bf12-155">Run the following two commands:</span></span>
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="0bf12-156">Si vous n’avez pas encore de fournisseur PIC dans votre environnement et que vous êtes en train de créer un nouveau fournisseur de PIC, vous n’avez pas besoin d’exécuter l’applet de action <STRONG>Remove-CsPublicProvider</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="0bf12-156">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="0bf12-157">Ajouté dans Lync Server 2013 CU5 &amp; le client de bureau Lync dans Office 2013 SP1, le NameDecorationRoutingDomain et NameDecorationExcludedDomainList améliorer la situation dans laquelle les utilisateurs de Lync qui ajoutent des contacts Skype ont besoin de « décorer » des domaines non Microsoft pour les identifier et les acheminer vers Skype (format : utilisateur (contoso. com) @msn. com).</span><span class="sxs-lookup"><span data-stu-id="0bf12-157">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="0bf12-158">Ces nouveaux paramètres permettent la mise en forme automatique de l’adresse que l’utilisateur entre dans la boîte de dialogue « Ajouter un contact Skype » avec NameDecorationRoutingDomain (qui doit être défini sur msn.com) si elle ne contient pas les domaines dans NameDecorationExcludedDomainList (actuellement, nous pouvons prendre en charge msn.com, live.com, Hotmail.com et outlook.com).</span><span class="sxs-lookup"><span data-stu-id="0bf12-158">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

        
        </div>

3.  <span data-ttu-id="0bf12-159">À partir d’un client Lync, vous pouvez désormais sélectionner Skype en tant que fournisseur de PIC et ajouter un client Skype en spécifiant son compte Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0bf12-159">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="0bf12-160">De plus, un utilisateur de Skype qui a fusionné et connecté avec son compte Microsoft peut envoyer une demande de contact à des utilisateurs de Lync.</span><span class="sxs-lookup"><span data-stu-id="0bf12-160">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="0bf12-161">Pour plus d’informations sur les comptes Microsoft, voir [qu’est-ce qu’un compte Microsoft ?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span><span class="sxs-lookup"><span data-stu-id="0bf12-161">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="0bf12-162">Pour plus d’informations sur l’ajout de clients à Lync, reportez-vous à la rubrique [utilisation de Lync-connectivité Skype dans Lync Server 2013 en tant qu’utilisateur final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span><span class="sxs-lookup"><span data-stu-id="0bf12-162">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>

4.  <span data-ttu-id="0bf12-163">Pour plus d’informations sur la modification des fournisseurs hébergés, voir « créer ou modifier des fournisseurs fédérés [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)SIP hébergés » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="0bf12-163">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="0bf12-164">Cette procédure termine les tâches d’administration qui doivent être effectuées sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="0bf12-164">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="0bf12-165">Vous êtes désormais configuré pour Lync-connectivité Skype.</span><span class="sxs-lookup"><span data-stu-id="0bf12-165">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<div>

## <a name="additional-resources"></a><span data-ttu-id="0bf12-166">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0bf12-166">Additional Resources</span></span>

[<span data-ttu-id="0bf12-167">Utilisation de la connectivité Lync-Skype dans Lync Server 2013 en tant qu’utilisateur final</span><span class="sxs-lookup"><span data-stu-id="0bf12-167">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[<span data-ttu-id="0bf12-168">Guide d’approvisionnement pour la connectivité Lync-Skype dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bf12-168">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

