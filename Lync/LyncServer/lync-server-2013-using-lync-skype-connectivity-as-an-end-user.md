---
title: 'Lync Server 2013 : Utilisation de la connectivité Lync-Skype en tant qu’utilisateur final'
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
ms.openlocfilehash: 5404a42b0d8e2052541ccb9f9178bf33408c2099
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a><span data-ttu-id="30709-102">Utilisation de la connectivité Lync-Skype dans Lync Server 2013 en tant qu’utilisateur final</span><span class="sxs-lookup"><span data-stu-id="30709-102">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30709-103">_**Dernière modification de la rubrique :** 2016-12-27_</span><span class="sxs-lookup"><span data-stu-id="30709-103">_**Topic Last Modified:** 2016-12-27_</span></span>

<span data-ttu-id="30709-104">Lync-Skype Connectivity permet aux utilisateurs de Skype et aux utilisateurs de Lync de s’ajouter aux contacts, d’échanger des messages instantanés et de passer des appels audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="30709-104">Lync-Skype Connectivity enables Skype users and Lync users to add each other as contacts, exchange instant messages and make audio and video calls.</span></span> <span data-ttu-id="30709-105">Lorsqu’un utilisateur de Skype ajoute un utilisateur Lync, un utilisateur Skype crée un contact dans Skype contenant l’URI (Uniform Resource Identifier) de l’utilisateur Lync.</span><span class="sxs-lookup"><span data-stu-id="30709-105">When a Skype user adds a Lync user, a Skype user will create a contact in Skype containing the session initiation protocol (SIP) uniform resource identifier (URI) of the Lync user.</span></span> <span data-ttu-id="30709-106">À l’inverse, quand un utilisateur de Lync ajoute un contact Skype, l’utilisateur de Lync crée un contact dans Lync qui contient le compte Microsoft (MSA) de l’utilisateur Skype, et non le nom d’utilisateur Skype.</span><span class="sxs-lookup"><span data-stu-id="30709-106">Conversely, when a Lync user adds a Skype contact, the Lync user will create a contact in Lync that will contain the Microsoft Account (MSA) of the Skype user, and not the Skype user name.</span></span>

<span data-ttu-id="30709-107">**Qu’est-ce qu’un MSA ?**</span><span class="sxs-lookup"><span data-stu-id="30709-107">**What is an MSA?**</span></span> <span data-ttu-id="30709-108">Les utilisateurs de Skype doivent se connecter à Skype avec un compte Microsoft (auparavant appelé Windows Live ID) pour communiquer avec des contacts Lync.</span><span class="sxs-lookup"><span data-stu-id="30709-108">Skype users must sign in to Skype with a Microsoft account (previously called Windows Live ID) in order to communicate with Lync contacts.</span></span><span data-ttu-id="30709-109">Un compte Microsoft repose sur la combinaison d’une adresse de messagerie et d’un mot de passe, que vous pouvez également utiliser pour vous connecter à des services tels que la technologie de stockage Microsoft OneDrive, Windows Phone, le service de jeu Microsoft Xbox LIVE Online et la messagerie Microsoft Outlook et client de collaboration (et, auparavant, service de messagerie Web Microsoft Hotmail ou Windows Live Messenger).</span><span class="sxs-lookup"><span data-stu-id="30709-109"> A Microsoft account consists of the combination of an email address and a password, which you can also use to sign in to services such as Microsoft OneDrive storage technology, Windows Phone, Microsoft Xbox LIVE online game service, and Microsoft Outlook messaging and collaboration client (and, previously, Microsoft Hotmail web-based e-mail service or Windows Live Messenger).</span></span><span data-ttu-id="30709-110">Si vous utilisez une adresse de messagerie et un mot de passe pour vous connecter à ces services, vous disposez déjà d’un compte Microsoft.</span><span class="sxs-lookup"><span data-stu-id="30709-110"> If you use an email address and a password to sign in to these or other services, you already have a Microsoft account.</span></span><span data-ttu-id="30709-111">Pour plus d’informations sur la création d’un compte Microsoft, reportez-vous [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061)à la page de connexion au compte Microsoft à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="30709-111"> For details about creating a Microsoft Account, see the Microsoft account sign-up page at [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061).</span></span> <span data-ttu-id="30709-112">Vous pouvez fusionner votre compte Skype existant avec votre compte Microsoft pour l’authentification unique, dans de nombreuses applications et services.</span><span class="sxs-lookup"><span data-stu-id="30709-112">You can merge your existing Skype account with your Microsoft account for single sign-on, across a variety of applications and services.</span></span> <span data-ttu-id="30709-113">Une fois le compte fusionné, l’utilisateur de Skype peut envoyer une demande de contact aux utilisateurs de Lync.</span><span class="sxs-lookup"><span data-stu-id="30709-113">Once the account is merged a Skype user can send a contact request to Lync users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="30709-114">Pour que les utilisateurs de Lync et Skype puissent communiquer de manière complète, les conditions suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="30709-114">In order for Lync and Skype users to fully communicate with each other, the following requirements must be met:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="30709-115">Les utilisateurs de Skype doivent être connectés à leur client Skype avec un compte Microsoft (MSA).</span><span class="sxs-lookup"><span data-stu-id="30709-115">Skype users must be logged into their Skype client with a Microsoft Account (MSA).</span></span></P>
> <LI>
> <P><span data-ttu-id="30709-116">Les utilisateurs de Lync doivent être activés pour la connectivité PIC (Public IM Connectivity) par leur administrateur Lync.</span><span class="sxs-lookup"><span data-stu-id="30709-116">Lync users must be enabled for public IM connectivity by their Lync administrator.</span></span></P>
> <LI>
> <P><span data-ttu-id="30709-117">Lorsqu’un utilisateur Skype ajoute un contact Lync, vérifiez que le mot Lync apparaît sous le nom du contact.</span><span class="sxs-lookup"><span data-stu-id="30709-117">When a Skype user adds a Lync contact, verify that the word Lync appears below the contact’s name.</span></span> <span data-ttu-id="30709-118">Cela indique qu’un URI Lync a été trouvé.</span><span class="sxs-lookup"><span data-stu-id="30709-118">This indicates that a Lync URI has been found.</span></span></P>
> <LI>
> <P><span data-ttu-id="30709-119">Lorsqu’un utilisateur Skype ajoute un contact Lync et que les résultats de la recherche ne sont pas retournés pour ce domaine Lync, le processus de mise en service de PIC n’est peut-être pas terminé ou le domaine Lync n’a pas encore été configuré.</span><span class="sxs-lookup"><span data-stu-id="30709-119">When a Skype user adds a Lync contact and zero search results are returned for that Lync domain, the PIC provisioning process may not have completed, or the Lync domain has not yet been set up.</span></span></P>
> <LI>
> <P><span data-ttu-id="30709-120">En fonction des paramètres de confidentialité de Lync et des utilisateurs Skype, la messagerie instantanée, la vidéo et la présence risquent de ne pas fonctionner tant que les nouveaux contacts ne sont pas acceptés par chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="30709-120">Depending on the privacy settings of the Lync and Skype users, IM, video, and presence may not work until the new contacts are accepted by each user.</span></span></P></LI></UL>



</div>

<span data-ttu-id="30709-121">**Pour ajouter un contact Skype à Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="30709-121">**To add a Skype contact to Lync 2013**</span></span>

1.  <span data-ttu-id="30709-122">Dans Lync, cliquez sur **Ajouter un contact, puis ajoutez un contact qui n’est pas dans ma société**.</span><span class="sxs-lookup"><span data-stu-id="30709-122">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="30709-123">Dans la liste des fournisseurs de contacts disponibles, sélectionnez **Skype**.</span><span class="sxs-lookup"><span data-stu-id="30709-123">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="30709-124">Dans le champ **adresse de messagerie instantanée** , entrez le compte Microsoft (MSA) de l’utilisateur Skype.</span><span class="sxs-lookup"><span data-stu-id="30709-124">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user.</span></span>

4.  <span data-ttu-id="30709-125">Dans la liste déroulante **Ajouter au groupe de contacts** , sélectionnez le groupe de contacts auquel vous souhaitez ajouter l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="30709-125">In the **Add to contact group** dropdown box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="30709-126">Dans la liste déroulante **définir la relation de confidentialité** , sélectionnez le paramètre de contact approprié, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="30709-126">In the **Set privacy relationship** dropdown box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="30709-127">L’utilisateur s’affiche désormais comme contact dans Lync.</span><span class="sxs-lookup"><span data-stu-id="30709-127">The user will now appear as a contact in Lync.</span></span> <span data-ttu-id="30709-128">Sélectionnez l’utilisateur, cliquez avec le bouton droit sur le nom d’utilisateur, puis cliquez sur **afficher la carte de visite** pour afficher les propriétés de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="30709-128">Select the user, right-click the user name, and click **See Contact Card** to view the user properties.</span></span> <span data-ttu-id="30709-129">Vous pouvez désormais passer un appel audio ou vidéo à l’aide de l’utilisateur Skype que vous venez d’ajouter.</span><span class="sxs-lookup"><span data-stu-id="30709-129">You can now establish an audio or video call with the newly added Skype user.</span></span>

<span data-ttu-id="30709-130">Pour plus d’informations sur la prise en charge des contacts, consultez [Ajouter un contact dans Lync](https://support.office.com/en-us/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).</span><span class="sxs-lookup"><span data-stu-id="30709-130">For additional information on support for contacts, see [Add a contact in Lync](https://support.office.com/en-us/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).</span></span>

<span data-ttu-id="30709-131">Lorsque le compte Microsoft d’un utilisateur Skype utilise un nom de domaine personnalisé, tel que <strong>Bob@contoso.com</strong> , un utilisateur de Lync peut ajouter ce compte Microsoft à Lync de deux manières :</span><span class="sxs-lookup"><span data-stu-id="30709-131">When a Skype user’s Microsoft account uses a custom domain name, such as <strong>bob@contoso.com</strong> , a Lync user can add that Microsoft account to Lync in two ways:</span></span>

1.  <span data-ttu-id="30709-132">Utilisez l’icône **Ajouter un contact** ou</span><span class="sxs-lookup"><span data-stu-id="30709-132">Use the **Add a Contact** icon, or</span></span>

2.  <span data-ttu-id="30709-133">Utilisez le champ **Rechercher une personne ou une salle ou un numéro de** téléphone.</span><span class="sxs-lookup"><span data-stu-id="30709-133">Use the **Find someone or a room, or a dial a number** field.</span></span>

<span data-ttu-id="30709-134">Dans chaque instance, l’utilisateur de Lync doit entrer l’adresse e-mail de l’utilisateur Skype au format suivant : <strong>utilisateur (nom de domaine) @msn. com</strong> .</span><span class="sxs-lookup"><span data-stu-id="30709-134">In each instance, the Lync user must enter the Skype user’s email in the following format: <strong>user(domain name)@msn.com</strong> .</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="30709-135">Cette étape n’est pas requise pour les comptes Microsoft qui utilisent les noms de domaine suivants : <STRONG>@live. com, @hotmail. com ou @outlook. com</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="30709-135">This step is not required for Microsoft accounts that use the following domain names: <STRONG>@live.com, @hotmail.com or @outlook.com</STRONG>.</span></span> <span data-ttu-id="30709-136">Pour plus d’informations sur les noms de domaine personnalisés pris en charge, voir <A href="https://support.microsoft.com/kb/897567">domaines de messagerie instantanée publics pris en charge</A>.</span><span class="sxs-lookup"><span data-stu-id="30709-136">For more information on supported custom domain names, see <A href="https://support.microsoft.com/kb/897567">Supported public IM domains</A>.</span></span>



</div>

<span data-ttu-id="30709-137">**Pour ajouter un contact Skype à Lync lors de l’utilisation d’un nom de domaine personnalisé**</span><span class="sxs-lookup"><span data-stu-id="30709-137">**To add a Skype contact to Lync when using a custom domain name**</span></span>

1.  <span data-ttu-id="30709-138">Dans Lync, cliquez sur **Ajouter un contact, puis ajoutez un contact qui n’est pas dans ma société**.</span><span class="sxs-lookup"><span data-stu-id="30709-138">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="30709-139">Dans la liste des fournisseurs de contacts disponibles, sélectionnez **Skype**.</span><span class="sxs-lookup"><span data-stu-id="30709-139">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="30709-140">Dans le champ **adresse de messagerie instantanée** , entrez le compte Microsoft (MSA) de l’utilisateur Skype au format <strong>utilisateur (nom de domaine) @msn. com</strong>.</span><span class="sxs-lookup"><span data-stu-id="30709-140">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user in the format <strong>user(domain name)@msn.com</strong>.</span></span> <span data-ttu-id="30709-141">Ainsi, pour l’utilisateur bob@contoso.com, l’entrée <strong>est Bob (contoso. com) @msn.<strong> com.</span><span class="sxs-lookup"><span data-stu-id="30709-141">So for user bob@contoso.com, the entry would be <strong>bob(contoso.com)@msn.com<strong> .</span></span>

4.  <span data-ttu-id="30709-142">Dans la zone de liste déroulante **Ajouter au groupe de contacts** , sélectionnez le groupe de contacts auquel vous souhaitez ajouter l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="30709-142">In the **Add to contact group** drop-down list box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="30709-143">Dans la zone de liste déroulante **définir la relation de confidentialité** , sélectionnez le paramètre de contact approprié, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="30709-143">In the **Set privacy relationship** drop-down list box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="30709-144">Un utilisateur de Lync peut également utiliser le champ **Rechercher une personne ou une salle ou composer un numéro** dans Lync et ajouter une adresse qui ressemble à l' <strong>utilisateur suivant (nom de domaine) @msn. com</strong> .</span><span class="sxs-lookup"><span data-stu-id="30709-144">A Lync user can also use the **Find someone or a room, or dial a number** field in Lync, and add an address that resembles the following <strong>user(domain name)@msn.com</strong> .</span></span> <span data-ttu-id="30709-145">Pour le compte Microsoft bob@contoso.com, l’entrée est <strong>Bob (contoso. com) @msn. com</strong> .</span><span class="sxs-lookup"><span data-stu-id="30709-145">So for the bob@contoso.com Microsoft account, the entry would be <strong>bob(contoso.com)@msn.com</strong> .</span></span>

7.  <span data-ttu-id="30709-146">Suivez les étapes 4 et 5 décrites plus haut dans cette procédure pour ajouter le contact à un groupe de contacts et pour sélectionner la relation de confidentialité appropriée.</span><span class="sxs-lookup"><span data-stu-id="30709-146">Follow steps 4 and 5 earlier in this procedure to add the contact to a contact group and to select the appropriate privacy relationship.</span></span>

<span data-ttu-id="30709-147">**Pour ajouter un contact Lync à Skype**</span><span class="sxs-lookup"><span data-stu-id="30709-147">**To add a Lync contact to Skype**</span></span>

1.  <span data-ttu-id="30709-148">Connectez-vous à Skype.</span><span class="sxs-lookup"><span data-stu-id="30709-148">Sign in to Skype.</span></span> <span data-ttu-id="30709-149">L’utilisateur Skype doit être connecté à son client Skype avec un compte Microsoft (MSA).</span><span class="sxs-lookup"><span data-stu-id="30709-149">The Skype user must be logged into their Skype client with a Microsoft Account (MSA).</span></span>

2.  <span data-ttu-id="30709-150">Sélectionnez l’icône Ajouter des contacts.</span><span class="sxs-lookup"><span data-stu-id="30709-150">Select the Add Contacts icon.</span></span>

3.  <span data-ttu-id="30709-151">Entrez l’URI SIP de l’utilisateur Lync.</span><span class="sxs-lookup"><span data-stu-id="30709-151">Enter the SIP URI of the Lync user.</span></span> <span data-ttu-id="30709-152">Par exemple, bob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="30709-152">For example, bob@contoso.com.</span></span>

4.  <span data-ttu-id="30709-153">Lorsque Skype trouve la correspondance dans les résultats de recherche, recherchez le mot **Lync** sous le nom de l’utilisateur Lync.</span><span class="sxs-lookup"><span data-stu-id="30709-153">When Skype finds the match in the search results, look for the word **Lync** below the Lync user’s name.</span></span> <span data-ttu-id="30709-154">Cela indique que Skype a trouvé l’URI SIP du client Lync.</span><span class="sxs-lookup"><span data-stu-id="30709-154">This indicates Skype successfully located the Lync client’s SIP URI.</span></span> <span data-ttu-id="30709-155">Cliquez sur le nom.</span><span class="sxs-lookup"><span data-stu-id="30709-155">Click the name.</span></span>

5.  <span data-ttu-id="30709-156">Dans le coin supérieur droit de la fenêtre, cliquez sur Ajouter aux contacts.</span><span class="sxs-lookup"><span data-stu-id="30709-156">In the top right corner of the window, click Add to Contacts.</span></span>

6.  <span data-ttu-id="30709-157">Le nouveau contact est désormais ajouté à votre liste de contacts, mais un point d’interrogation est affiché au lieu de son icône de statut jusqu’à ce qu’il accepte votre demande.</span><span class="sxs-lookup"><span data-stu-id="30709-157">The new contact is now added to your contact list, but you’ll see a question mark instead of their status icon until they accept your request.</span></span> <span data-ttu-id="30709-158">Lorsque votre contact a accepté votre demande, vous pouvez voir quand il est en ligne, lancer des conversations par messagerie instantanée et effectuer des appels audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="30709-158">When your new contact accepts your request, you will be able to see when they are online, initiate IM conversations, and make audio and video calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="30709-159">L’administrateur du serveur Lync doit configurer les paramètres de stratégie de l’utilisateur Lync pour autoriser les demandes entrantes.</span><span class="sxs-lookup"><span data-stu-id="30709-159">The Lync Server administrator must configure the Lync user’s policy settings to allow incoming requests.</span></span> <span data-ttu-id="30709-160">Si ce n’est pas le cas, l’utilisateur de Lync n’aura pas reçu de demandes de contact de l’utilisateur Skype.</span><span class="sxs-lookup"><span data-stu-id="30709-160">If not, the Lync user will not receive contact requests from the Skype user.</span></span> <span data-ttu-id="30709-161">En fonction de la configuration des paramètres de stratégie de l’utilisateur Lync, la demande d’ajout de l’utilisateur Skype apparaît sous l’onglet <STRONG>nouveau</STRONG> du client Lync. Pour commencer à communiquer avec l’utilisateur Skype, l’utilisateur de Lync doit ajouter l’utilisateur Skype à la liste de favoris ou à une liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="30709-161">Depending on the configuration of the Lync user’s policy settings, the request to add the Skype user will appear on the Lync client’s <STRONG>New</STRONG> tab. To begin communicating with the Skype user, the Lync user must add the Skype user to either the Favorites list or a contact list.</span></span> <span data-ttu-id="30709-162">L’image ci-dessous montre l’emplacement du <STRONG>nouvel</STRONG> onglet dans le client Lync.</span><span class="sxs-lookup"><span data-stu-id="30709-162">The image below shows the location of the <STRONG>New</STRONG> tab in the Lync client.</span></span>

    
    </div>

<span data-ttu-id="30709-163">Un utilisateur de Lync doit configurer des alertes Lync pour s’assurer que les demandes envoyées à partir d’un utilisateur Skype apparaissent et qu’ils peuvent être détectés par l’utilisateur de Lync.</span><span class="sxs-lookup"><span data-stu-id="30709-163">A Lync user must configure Lync alerts to ensure that requests sent from a Skype user appear and are discoverable by the Lync user.</span></span> <span data-ttu-id="30709-164">Pour configurer les alertes Lync, suivez la procédure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="30709-164">To configure Lync alerts, complete the procedure that follows.</span></span>

<span data-ttu-id="30709-165">**Pour configurer les alertes Lync**</span><span class="sxs-lookup"><span data-stu-id="30709-165">**To configure Lync Alerts**</span></span>

1.  <span data-ttu-id="30709-166">Dans le client Lync, cliquez sur l’icône **options** .</span><span class="sxs-lookup"><span data-stu-id="30709-166">From the Lync client, click the **Options** icon.</span></span>

2.  <span data-ttu-id="30709-167">Sélectionnez **alertes**.</span><span class="sxs-lookup"><span data-stu-id="30709-167">Select **Alerts**.</span></span>

3.  <span data-ttu-id="30709-168">Sous **alertes générales**, activez la case à cocher m’avertir **quand une personne m’ajoute à sa liste de contacts**.</span><span class="sxs-lookup"><span data-stu-id="30709-168">Under **General alerts**, check **Tell me when someone adds me to his or her contact list**.</span></span>

4.  <span data-ttu-id="30709-169">Sous **contacts n’utilisant pas Lync**, sélectionnez **autoriser les invitations, mais bloquer toutes les autres communications**.</span><span class="sxs-lookup"><span data-stu-id="30709-169">Under **Contacts not using Lync**, select **Allow invites but block all other communications**.</span></span>

5.  <span data-ttu-id="30709-170">Cliquez sur **OK** pour fermer la fenêtre d’options.</span><span class="sxs-lookup"><span data-stu-id="30709-170">Click **OK** to close the Options window.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

