---
title: 'Lync Server 2013 : utilisation de la connectivité Lync-Skype en tant qu’utilisateur final'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Lync-Skype connectivity as an end user
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440175(v=OCS.15)
ms:contentKeyID: 57793365
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6971ef2d6fb08838a4fcf71f4fec8097a7f9e47
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a><span data-ttu-id="ec5dd-102">Utilisation de la connectivité Lync-Skype dans Lync Server 2013 en tant qu’utilisateur final</span><span class="sxs-lookup"><span data-stu-id="ec5dd-102">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec5dd-103">_**Dernière modification de la rubrique :** 2016-12-27_</span><span class="sxs-lookup"><span data-stu-id="ec5dd-103">_**Topic Last Modified:** 2016-12-27_</span></span>

<span data-ttu-id="ec5dd-104">Lync-Skype Connectivity permet aux utilisateurs Skype et aux utilisateurs de Lync de s’ajouter eux-mêmes sous forme de contacts, d’échanger des messages instantanés et d’effectuer des appels audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-104">Lync-Skype Connectivity enables Skype users and Lync users to add each other as contacts, exchange instant messages and make audio and video calls.</span></span> <span data-ttu-id="ec5dd-105">Lorsqu’un utilisateur Skype ajoute un utilisateur Lync, un utilisateur Skype crée un contact dans Skype contenant l’URI (Uniform Resource Identifier) SIP (Session Initiation Protocol) de l’utilisateur Lync.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-105">When a Skype user adds a Lync user, a Skype user will create a contact in Skype containing the session initiation protocol (SIP) uniform resource identifier (URI) of the Lync user.</span></span> <span data-ttu-id="ec5dd-106">À l’inverse, lorsqu’un utilisateur Lync ajoute un contact Skype, l’utilisateur de Lync crée un contact dans Lync qui contiendra le compte Microsoft (MSA) de l’utilisateur Skype, et non le nom d’utilisateur Skype.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-106">Conversely, when a Lync user adds a Skype contact, the Lync user will create a contact in Lync that will contain the Microsoft Account (MSA) of the Skype user, and not the Skype user name.</span></span>

<span data-ttu-id="ec5dd-107">**Qu’est-ce qu’un MSA ?**</span><span class="sxs-lookup"><span data-stu-id="ec5dd-107">**What is an MSA?**</span></span> <span data-ttu-id="ec5dd-108">Les utilisateurs de Skype doivent se connecter à Skype à l’aide d’un compte Microsoft (anciennement appelé Windows Live ID) pour communiquer avec les contacts Lync.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-108">Skype users must sign in to Skype with a Microsoft account (previously called Windows Live ID) in order to communicate with Lync contacts.</span></span><span data-ttu-id="ec5dd-109">Un compte Microsoft est constitué de la combinaison d’une adresse de messagerie et d’un mot de passe, que vous pouvez également utiliser pour vous connecter à des services tels que la technologie de stockage Microsoft OneDrive, Windows Phone, le service de jeux Microsoft Xbox LIVE Online et la messagerie Microsoft Outlook. et le client de collaboration (et, auparavant, le service de messagerie Web Microsoft Hotmail ou Windows Live Messenger).</span><span class="sxs-lookup"><span data-stu-id="ec5dd-109"> A Microsoft account consists of the combination of an email address and a password, which you can also use to sign in to services such as Microsoft OneDrive storage technology, Windows Phone, Microsoft Xbox LIVE online game service, and Microsoft Outlook messaging and collaboration client (and, previously, Microsoft Hotmail web-based e-mail service or Windows Live Messenger).</span></span><span data-ttu-id="ec5dd-110">Si vous utilisez une adresse de messagerie et un mot de passe pour vous connecter à ces services ou à d’autres services, vous disposez déjà d’un compte Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-110"> If you use an email address and a password to sign in to these or other services, you already have a Microsoft account.</span></span><span data-ttu-id="ec5dd-111">Pour plus d’informations sur la création d’un compte Microsoft, reportez-vous [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061)à la page d’inscription au compte Microsoft à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-111"> For details about creating a Microsoft Account, see the Microsoft account sign-up page at [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061).</span></span> <span data-ttu-id="ec5dd-112">Vous pouvez fusionner votre compte Skype existant avec votre compte Microsoft pour l’authentification unique, par le biais d’une variété d’applications et de services.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-112">You can merge your existing Skype account with your Microsoft account for single sign-on, across a variety of applications and services.</span></span> <span data-ttu-id="ec5dd-113">Une fois le compte fusionné, un utilisateur de Skype peut envoyer une demande de contact aux utilisateurs de Lync.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-113">Once the account is merged a Skype user can send a contact request to Lync users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ec5dd-114">Pour permettre aux utilisateurs Lync et Skype de communiquer entièrement les uns avec les autres, les conditions suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="ec5dd-114">In order for Lync and Skype users to fully communicate with each other, the following requirements must be met:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="ec5dd-115">Les utilisateurs de Skype doivent être connectés à leur client Skype à l’aide d’un compte Microsoft (MSA).</span><span class="sxs-lookup"><span data-stu-id="ec5dd-115">Skype users must be logged into their Skype client with a Microsoft Account (MSA).</span></span></P>
> <LI>
> <P><span data-ttu-id="ec5dd-116">Les utilisateurs de Lync doivent être activés pour la connectivité PIC par leur administrateur Lync.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-116">Lync users must be enabled for public IM connectivity by their Lync administrator.</span></span></P>
> <LI>
> <P><span data-ttu-id="ec5dd-117">Lorsqu’un utilisateur Skype ajoute un contact Lync, vérifiez que le mot Lync apparaît sous le nom du contact.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-117">When a Skype user adds a Lync contact, verify that the word Lync appears below the contact’s name.</span></span> <span data-ttu-id="ec5dd-118">Cela indique qu’un URI Lync a été trouvé.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-118">This indicates that a Lync URI has been found.</span></span></P>
> <LI>
> <P><span data-ttu-id="ec5dd-119">Lorsqu’un utilisateur Skype ajoute un contact Lync et que les résultats de la recherche ne sont pas renvoyés pour ce domaine Lync, le processus de mise en service PIC n’est peut-être pas terminé ou le domaine Lync n’a pas encore été configuré.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-119">When a Skype user adds a Lync contact and zero search results are returned for that Lync domain, the PIC provisioning process may not have completed, or the Lync domain has not yet been set up.</span></span></P>
> <LI>
> <P><span data-ttu-id="ec5dd-120">En fonction des paramètres de confidentialité des utilisateurs Lync et Skype, la messagerie instantanée, la vidéo et la présence peuvent ne pas fonctionner tant que les nouveaux contacts ne sont pas acceptés par chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-120">Depending on the privacy settings of the Lync and Skype users, IM, video, and presence may not work until the new contacts are accepted by each user.</span></span></P></LI></UL>



</div>

<span data-ttu-id="ec5dd-121">**Pour ajouter un contact Skype à Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="ec5dd-121">**To add a Skype contact to Lync 2013**</span></span>

1.  <span data-ttu-id="ec5dd-122">Dans Lync, cliquez sur **Ajouter un contact, puis ajoutez un contact qui n’est pas dans mon organisation**.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-122">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="ec5dd-123">Dans la liste des fournisseurs de contacts disponibles, sélectionnez **Skype**.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-123">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="ec5dd-124">Dans le champ **adresse de messagerie instantanée** , entrez le compte Microsoft (MSA) de l’utilisateur Skype.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-124">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user.</span></span>

4.  <span data-ttu-id="ec5dd-125">Dans la zone de liste déroulante **Ajouter au groupe de contacts** , sélectionnez un groupe de contacts auquel ajouter l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-125">In the **Add to contact group** dropdown box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="ec5dd-126">Dans la liste déroulante **définir la relation de confidentialité** , sélectionnez le paramètre de contact approprié, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-126">In the **Set privacy relationship** dropdown box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="ec5dd-127">L’utilisateur s’affiche désormais en tant que contact dans Lync.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-127">The user will now appear as a contact in Lync.</span></span> <span data-ttu-id="ec5dd-128">Sélectionnez l’utilisateur, cliquez avec le bouton droit sur le nom de l’utilisateur, puis cliquez sur **afficher la carte de visite** pour afficher les propriétés de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-128">Select the user, right-click the user name, and click **See Contact Card** to view the user properties.</span></span> <span data-ttu-id="ec5dd-129">Vous pouvez désormais établir un appel audio ou vidéo avec le nouvel utilisateur Skype ajouté.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-129">You can now establish an audio or video call with the newly added Skype user.</span></span>

<span data-ttu-id="ec5dd-130">Pour plus d’informations sur la prise en charge des contacts, consultez [la rubrique ajouter un contact dans Lync](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).</span><span class="sxs-lookup"><span data-stu-id="ec5dd-130">For additional information on support for contacts, see [Add a contact in Lync](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).</span></span>

<span data-ttu-id="ec5dd-131">Lorsque le compte Microsoft d’un utilisateur Skype utilise un nom de domaine personnalisé, tel que <strong>Bob@contoso.com</strong> , un utilisateur Lync peut ajouter ce compte Microsoft à Lync de deux manières :</span><span class="sxs-lookup"><span data-stu-id="ec5dd-131">When a Skype user’s Microsoft account uses a custom domain name, such as <strong>bob@contoso.com</strong> , a Lync user can add that Microsoft account to Lync in two ways:</span></span>

1.  <span data-ttu-id="ec5dd-132">Utilisez l’icône **Ajouter un contact** ou</span><span class="sxs-lookup"><span data-stu-id="ec5dd-132">Use the **Add a Contact** icon, or</span></span>

2.  <span data-ttu-id="ec5dd-133">Utilisez la zone **Rechercher une personne ou une salle, ou un champ de numéro de** téléphone.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-133">Use the **Find someone or a room, or a dial a number** field.</span></span>

<span data-ttu-id="ec5dd-134">Dans chaque instance, l’utilisateur Lync doit entrer le courrier électronique de l’utilisateur Skype dans le format suivant : <strong>utilisateur (nom de domaine) @msn. com</strong> .</span><span class="sxs-lookup"><span data-stu-id="ec5dd-134">In each instance, the Lync user must enter the Skype user’s email in the following format: <strong>user(domain name)@msn.com</strong> .</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ec5dd-135">Cette étape n’est pas obligatoire pour les comptes Microsoft qui utilisent les noms de domaine suivants : <STRONG>@live. com, @hotmail. com ou @outlook. com</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-135">This step is not required for Microsoft accounts that use the following domain names: <STRONG>@live.com, @hotmail.com or @outlook.com</STRONG>.</span></span> <span data-ttu-id="ec5dd-136">Pour plus d’informations sur les noms de domaine personnalisés pris en charge, consultez la rubrique <A href="https://support.microsoft.com/kb/897567">domaines de messagerie instantanée publics pris en charge</A>.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-136">For more information on supported custom domain names, see <A href="https://support.microsoft.com/kb/897567">Supported public IM domains</A>.</span></span>



</div>

<span data-ttu-id="ec5dd-137">**Pour ajouter un contact Skype à Lync lors de l’utilisation d’un nom de domaine personnalisé**</span><span class="sxs-lookup"><span data-stu-id="ec5dd-137">**To add a Skype contact to Lync when using a custom domain name**</span></span>

1.  <span data-ttu-id="ec5dd-138">Dans Lync, cliquez sur **Ajouter un contact, puis ajoutez un contact qui n’est pas dans mon organisation**.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-138">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="ec5dd-139">Dans la liste des fournisseurs de contacts disponibles, sélectionnez **Skype**.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-139">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="ec5dd-140">Dans le champ **adresse de messagerie instantanée** , entrez le compte Microsoft (MSA) de l’utilisateur Skype au format <strong>utilisateur (nom de domaine) @msn. com</strong>.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-140">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user in the format <strong>user(domain name)@msn.com</strong>.</span></span> <span data-ttu-id="ec5dd-141">Ainsi, pour l’utilisateur bob@contoso.com, l’entrée <strong>serait Bob (contoso. com) @msn.<strong> com.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-141">So for user bob@contoso.com, the entry would be <strong>bob(contoso.com)@msn.com<strong> .</span></span>

4.  <span data-ttu-id="ec5dd-142">Dans la zone de liste déroulante **Ajouter au groupe de contacts** , sélectionnez un groupe de contacts auquel ajouter l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-142">In the **Add to contact group** drop-down list box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="ec5dd-143">Dans la zone de liste déroulante **définir la relation de confidentialité** , sélectionnez le paramètre de contact approprié, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-143">In the **Set privacy relationship** drop-down list box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="ec5dd-144">Un utilisateur Lync peut également utiliser la commande **Rechercher une personne ou une salle, ou composer un** champ de numéro dans Lync, et ajouter une adresse semblable à l' <strong>utilisateur suivant (nom de domaine) @msn. com</strong> .</span><span class="sxs-lookup"><span data-stu-id="ec5dd-144">A Lync user can also use the **Find someone or a room, or dial a number** field in Lync, and add an address that resembles the following <strong>user(domain name)@msn.com</strong> .</span></span> <span data-ttu-id="ec5dd-145">Ainsi, pour le compte Microsoft bob@contoso.com, l’entrée serait <strong>Bob (contoso. com) @msn. com</strong> .</span><span class="sxs-lookup"><span data-stu-id="ec5dd-145">So for the bob@contoso.com Microsoft account, the entry would be <strong>bob(contoso.com)@msn.com</strong> .</span></span>

7.  <span data-ttu-id="ec5dd-146">Suivez les étapes 4 et 5 plus haut dans cette procédure pour ajouter le contact à un groupe de contacts et sélectionner la relation de confidentialité appropriée.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-146">Follow steps 4 and 5 earlier in this procedure to add the contact to a contact group and to select the appropriate privacy relationship.</span></span>

<span data-ttu-id="ec5dd-147">**Pour ajouter un contact Lync à Skype**</span><span class="sxs-lookup"><span data-stu-id="ec5dd-147">**To add a Lync contact to Skype**</span></span>

1.  <span data-ttu-id="ec5dd-148">Connectez-vous à Skype.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-148">Sign in to Skype.</span></span> <span data-ttu-id="ec5dd-149">L’utilisateur Skype doit être connecté à son client Skype à l’aide d’un compte Microsoft (MSA).</span><span class="sxs-lookup"><span data-stu-id="ec5dd-149">The Skype user must be logged into their Skype client with a Microsoft Account (MSA).</span></span>

2.  <span data-ttu-id="ec5dd-150">Sélectionnez l’icône Ajouter des contacts.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-150">Select the Add Contacts icon.</span></span>

3.  <span data-ttu-id="ec5dd-151">Entrez l’URI SIP de l’utilisateur Lync.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-151">Enter the SIP URI of the Lync user.</span></span> <span data-ttu-id="ec5dd-152">(par exemple, bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ec5dd-152">For example, bob@contoso.com.</span></span>

4.  <span data-ttu-id="ec5dd-153">Lorsque Skype trouve la correspondance dans les résultats de la recherche, recherchez le mot **Lync** sous le nom de l’utilisateur Lync.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-153">When Skype finds the match in the search results, look for the word **Lync** below the Lync user’s name.</span></span> <span data-ttu-id="ec5dd-154">Cela indique que Skype a réussi à localiser l’URI SIP du client Lync.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-154">This indicates Skype successfully located the Lync client’s SIP URI.</span></span> <span data-ttu-id="ec5dd-155">Cliquez sur le nom.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-155">Click the name.</span></span>

5.  <span data-ttu-id="ec5dd-156">Dans le coin supérieur droit de la fenêtre, cliquez sur Ajouter aux contacts.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-156">In the top right corner of the window, click Add to Contacts.</span></span>

6.  <span data-ttu-id="ec5dd-157">Le nouveau contact est maintenant ajouté à votre liste de contacts, mais un point d’interrogation s’affiche au lieu de son icône d’État jusqu’à ce qu’il accepte votre requête.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-157">The new contact is now added to your contact list, but you’ll see a question mark instead of their status icon until they accept your request.</span></span> <span data-ttu-id="ec5dd-158">Lorsque votre nouveau contact accepte votre demande, vous pouvez voir quand il est en ligne, initier des conversations par messagerie instantanée et émettre des appels audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-158">When your new contact accepts your request, you will be able to see when they are online, initiate IM conversations, and make audio and video calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ec5dd-159">L’administrateur Lync Server doit configurer les paramètres de stratégie de l’utilisateur Lync pour autoriser les demandes entrantes.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-159">The Lync Server administrator must configure the Lync user’s policy settings to allow incoming requests.</span></span> <span data-ttu-id="ec5dd-160">Si ce n’est pas le cas, l’utilisateur de Lync ne reçoit pas de demandes de contact de la part de l’utilisateur Skype.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-160">If not, the Lync user will not receive contact requests from the Skype user.</span></span> <span data-ttu-id="ec5dd-161">En fonction de la configuration des paramètres de stratégie de l’utilisateur Lync, la demande d’ajout de l’utilisateur Skype apparaît dans le <STRONG>nouvel</STRONG> onglet du client Lync. Pour commencer à communiquer avec l’utilisateur Skype, l’utilisateur de Lync doit ajouter l’utilisateur Skype à la liste des favoris ou à une liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-161">Depending on the configuration of the Lync user’s policy settings, the request to add the Skype user will appear on the Lync client’s <STRONG>New</STRONG> tab. To begin communicating with the Skype user, the Lync user must add the Skype user to either the Favorites list or a contact list.</span></span> <span data-ttu-id="ec5dd-162">L’image ci-dessous montre l’emplacement du <STRONG>nouvel</STRONG> onglet dans le client Lync.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-162">The image below shows the location of the <STRONG>New</STRONG> tab in the Lync client.</span></span>

    
    </div>

<span data-ttu-id="ec5dd-163">Un utilisateur Lync doit configurer des alertes Lync pour s’assurer que les demandes envoyées à partir d’un utilisateur Skype apparaissent et sont détectables par l’utilisateur de Lync.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-163">A Lync user must configure Lync alerts to ensure that requests sent from a Skype user appear and are discoverable by the Lync user.</span></span> <span data-ttu-id="ec5dd-164">Pour configurer les alertes Lync, exécutez la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-164">To configure Lync alerts, complete the procedure that follows.</span></span>

<span data-ttu-id="ec5dd-165">**Pour configurer les alertes Lync**</span><span class="sxs-lookup"><span data-stu-id="ec5dd-165">**To configure Lync Alerts**</span></span>

1.  <span data-ttu-id="ec5dd-166">À partir du client Lync, cliquez sur l’icône **options** .</span><span class="sxs-lookup"><span data-stu-id="ec5dd-166">From the Lync client, click the **Options** icon.</span></span>

2.  <span data-ttu-id="ec5dd-167">Sélectionnez **alertes**.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-167">Select **Alerts**.</span></span>

3.  <span data-ttu-id="ec5dd-168">Sous **alertes générales**, sélectionnez m' **indiquer quand quelqu’un m’ajoute à sa liste de contacts**.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-168">Under **General alerts**, check **Tell me when someone adds me to his or her contact list**.</span></span>

4.  <span data-ttu-id="ec5dd-169">Sous **contacts n’utilisant pas Lync**, sélectionnez **autoriser les invitations, mais bloquer toutes les autres communications**.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-169">Under **Contacts not using Lync**, select **Allow invites but block all other communications**.</span></span>

5.  <span data-ttu-id="ec5dd-170">Cliquez sur **OK** pour fermer la fenêtre Options.</span><span class="sxs-lookup"><span data-stu-id="ec5dd-170">Click **OK** to close the Options window.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

