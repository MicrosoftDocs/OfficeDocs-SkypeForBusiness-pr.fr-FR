---
title: 'Lync Server 2013 : utilisation de l’authentification à deux facteurs avec le client Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbd45e3e54ec9fb6b1a9757c0a46a1454901f749
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a><span data-ttu-id="7b7d9-102">Utilisation de l’authentification à deux facteurs avec le client Lync et Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b7d9-102">Using two-factor authentication with Lync client and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b7d9-103">_**Dernière modification de la rubrique :** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="7b7d9-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="7b7d9-104">Cette rubrique décrit comment tirer parti de l’authentification à deux facteurs avec le client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-104">This topic described how to take advantage of two-factor authentication with Lync 2013 client.</span></span>

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a><span data-ttu-id="7b7d9-105">Connexion à Lync 2013 pour la première fois</span><span class="sxs-lookup"><span data-stu-id="7b7d9-105">Sign in to Lync 2013 for the first time</span></span>

<span data-ttu-id="7b7d9-106">Vos informations de connexion Lync sont généralement configurées automatiquement lors de l’installation de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-106">Your Lync sign-in information is usually configured automatically when Lync 2013 is installed.</span></span> <span data-ttu-id="7b7d9-107">Toutefois, la première fois que vous utilisez Lync, vous devrez peut-être démarrer manuellement le client.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-107">But the first time you use Lync, you might have to manually start the client.</span></span>

<span data-ttu-id="7b7d9-108">**Pour vous connecter à Lync pour la première fois**</span><span class="sxs-lookup"><span data-stu-id="7b7d9-108">**To sign in to Lync for the first time**</span></span>

1.  <span data-ttu-id="7b7d9-109">Ouvrez une session sur le réseau de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-109">Log on to your organization’s network.</span></span>

2.  <span data-ttu-id="7b7d9-110">Sélectionnez **Démarrer** \> **tous les programmes** \> **Microsoft \> Lync Lync 2013**.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-110">Select **Start** \> **All Programs** \> **Microsoft Lync \> Lync 2013**.</span></span>
    
    <span data-ttu-id="7b7d9-111">L’écran de connexion Lync doit s’afficher.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-111">You should see the Lync sign-in screen.</span></span>
    
      - <span data-ttu-id="7b7d9-112">Si la zone adresse de connexion est déjà renseignée, vérifiez que l’adresse indiquée est correcte.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-112">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
      - <span data-ttu-id="7b7d9-113">Si ce n’est pas le cas, ou si la zone est vide, entrez votre adresse de connexion Lync (il s’agit généralement de la même chose que votre adresse de messagerie).</span><span class="sxs-lookup"><span data-stu-id="7b7d9-113">If it’s not correct, or if the box is empty, enter your Lync sign-in address (this is usually the same as your email address).</span></span>
    
      - <span data-ttu-id="7b7d9-114">Si une zone de mot de passe vide est affichée, ajoutez votre mot de passe.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-114">If an empty password box is displayed, add your password.</span></span>

3.  <span data-ttu-id="7b7d9-115">Sélectionnez **connexion**.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-115">Select **Sign-in**.</span></span>

</div>

<div>

## <a name="sign-out-of-lync"></a><span data-ttu-id="7b7d9-116">Se déconnecter de Lync</span><span class="sxs-lookup"><span data-stu-id="7b7d9-116">Sign out of Lync</span></span>

<span data-ttu-id="7b7d9-117">Lorsque vous avez terminé d’utiliser Lync, vous pouvez fermer l’affichage, vous déconnecter de votre session ou quitter le programme, tout cela à partir du menu fichier.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-117">When you’re finished using Lync, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="7b7d9-118">Le tableau suivant décrit les différences entre les options.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-118">The following table explains the differences in the options.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b7d9-119">Option</span><span class="sxs-lookup"><span data-stu-id="7b7d9-119">Option</span></span></th>
<th><span data-ttu-id="7b7d9-120">Fonction</span><span class="sxs-lookup"><span data-stu-id="7b7d9-120">What it does</span></span></th>
<th><span data-ttu-id="7b7d9-121">Comment l’effectuer</span><span class="sxs-lookup"><span data-stu-id="7b7d9-121">How to perform it</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b7d9-122">Fermer</span><span class="sxs-lookup"><span data-stu-id="7b7d9-122">Close</span></span></p></td>
<td><p><span data-ttu-id="7b7d9-123">Ferme votre affichage Lync, mais laisse s’exécuter la session Lync identifiée avec votre ID d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-123">Closes your Lync display but lets the Lync session identified with your user ID continue to run.</span></span> <span data-ttu-id="7b7d9-124">Cela vous permet de continuer à recevoir des notifications et d’interagir avec d’autres personnes.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-124">This is so you can continue to get notifications and interact with others.</span></span></p>
<p><span data-ttu-id="7b7d9-125">Vous pouvez rétablir l’affichage à tout moment en cliquant sur l’icône Lync dans la barre des tâches ou dans la zone de notification en bas de l’écran.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-125">You can get the display back at any time by clicking the Lync icon on the taskbar or the notification area at the bottom of your screen.</span></span></p></td>
<td><p><span data-ttu-id="7b7d9-126">Dans la fenêtre principale Lync, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="7b7d9-126">On the Lync main window, do one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="7b7d9-127">Sélectionnez le bouton <strong>options</strong> , puis sélectionnez <strong>fichier</strong> &gt; <strong>Fermer</strong>.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-127">Select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Close</strong>.</span></span></p></li>
<li><p><span data-ttu-id="7b7d9-128">Cliquez sur le bouton <strong>Fermer</strong> (X) dans le coin supérieur droit de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-128">Click the <strong>Close</strong> button (X) in the upper-right corner of the window.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b7d9-129">Déconnexion</span><span class="sxs-lookup"><span data-stu-id="7b7d9-129">Sign out</span></span></p></td>
<td><p><span data-ttu-id="7b7d9-130">Met fin à la session Lync associée à votre ID d’utilisateur, mais Lync continue de s’exécuter en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-130">Ends the Lync session associated with your user ID, but Lync continues to run in the background.</span></span> <span data-ttu-id="7b7d9-131">Lorsque vous vous déconnectez, la fenêtre de connexion s’affiche.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-131">When you sign out, the sign-in window will appear.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="7b7d9-132">Sélectionnez <STRONG>Supprimer mes informations de connexion</STRONG> lorsque vous vous déconnectez pour supprimer l’enregistrement de votre ID de connexion et de votre mot de passe de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-132">Select <STRONG>Delete my sign-in information</STRONG> when you sign out to remove the record of your logon ID and password from the computer.</span></span> <span data-ttu-id="7b7d9-133">En procédant ainsi, il peut être plus facile pour les utilisateurs de la prise en charge de résoudre les problèmes de connexion.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-133">Doing this might make it easier for support people to troubleshoot sign-in issues.</span></span> <span data-ttu-id="7b7d9-134">Vous pouvez également vous assurer que vos informations de connexion sont plus sécurisées en rendant les utilisateurs non autorisés difficiles à se connecter avec vos informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-134">It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span>


</div></td>
<td><p><span data-ttu-id="7b7d9-135">Dans la fenêtre principale Lync <strong>, sélectionnez le</strong> &gt; bouton <strong>options</strong> , puis <strong>déconnectez-vous</strong>.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-135">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Sign Out</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b7d9-136">Quitter</span><span class="sxs-lookup"><span data-stu-id="7b7d9-136">Exit</span></span></p></td>
<td><p><span data-ttu-id="7b7d9-137">Termine votre session Lync et arrête Lync sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-137">Ends your Lync session and shuts down Lync on your computer.</span></span> <span data-ttu-id="7b7d9-138">Une fois la sortie terminée, si vous voulez redémarrer Lync, sélectionnez <strong>Démarrer</strong> &gt; <strong>tous les programmes</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-138">After exiting, if you want to restart Lync, select <strong>Start</strong> &gt; <strong>All Programs</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7b7d9-139">Dans la fenêtre principale Lync, sélectionnez le bouton <strong>options</strong> , puis sélectionnez <strong></strong> &gt; <strong>quitter</strong>.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-139">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Exit</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a><span data-ttu-id="7b7d9-140">Se connecter à Lync à l’aide d’une carte à puce</span><span class="sxs-lookup"><span data-stu-id="7b7d9-140">Sign in to Lync with a Smart Card</span></span>

<span data-ttu-id="7b7d9-141">Certaines organisations utilisent désormais un processus de connexion en plusieurs étapes, appelé authentification à deux facteurs, pour renforcer la sécurité de leurs utilisateurs Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-141">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their Lync 2013 users.</span></span> <span data-ttu-id="7b7d9-142">Si vous envisagez d’utiliser cette option, vous aurez besoin d’une « carte à puce » pour vous connecter à Lync.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-142">If you’re expected to use this option, you’ll need a “smart card” to sign in to Lync.</span></span> <span data-ttu-id="7b7d9-143">Les cartes à puce sont de deux types, physiques et virtuels :</span><span class="sxs-lookup"><span data-stu-id="7b7d9-143">Smart cards come in two varieties, physical and virtual:</span></span>

  - <span data-ttu-id="7b7d9-144">**Physique**   de la taille d’une carte de crédit.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-144">**Physical**   About the size of a credit card.</span></span> <span data-ttu-id="7b7d9-145">Vous l’insérez dans un lecteur de carte à puce lorsque vous vous connectez.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-145">You insert it into a smart card reader when you log in.</span></span>

  - <span data-ttu-id="7b7d9-146">**Virtual**   n’est pas un objet physique, mais un identificateur électronique qui est écrit sur une puce spéciale sur votre ordinateur, qui, par essence, crée la carte à puce sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-146">**Virtual**   Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="7b7d9-147">Disponible uniquement pour les ordinateurs Windows 8 qui contiennent le processeur TPM (Trusted Platform Module).</span><span class="sxs-lookup"><span data-stu-id="7b7d9-147">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>

<div>

## <a name="enroll-your-smart-card"></a><span data-ttu-id="7b7d9-148">Inscrire votre carte à puce</span><span class="sxs-lookup"><span data-stu-id="7b7d9-148">Enroll your smart card</span></span>

<span data-ttu-id="7b7d9-149">Avant de pouvoir vous connecter avec une carte à puce, la carte doit être « inscrite », c’est-à-dire que vos informations d’identification utilisateur doivent être identifiées avec la carte.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-149">Before you can sign in with a smart card, the card must be “enrolled”—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="7b7d9-150">C’est le cas si la carte est physique ou virtuelle.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-150">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="7b7d9-151">Ce processus a peut-être déjà été effectué par votre administrateur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-151">This process may already been carried out by your Lync Server administrator.</span></span> <span data-ttu-id="7b7d9-152">Vérifiez avec eux si vous ne savez pas si cela a été fait.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-152">Check with them if you’re not sure whether that has been done.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7b7d9-153">Étant donné que chaque carte à puce virtuelle est associée uniquement au périphérique sur lequel elle est installée, une carte distincte doit être entrée pour chaque ordinateur Windows 8 que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-153">Since each virtual smart card is associated only with the device it’s installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span>



</div>

<span data-ttu-id="7b7d9-154">**Pour inscrire manuellement votre carte à puce**</span><span class="sxs-lookup"><span data-stu-id="7b7d9-154">**To manually enroll your smart card**</span></span>

1.  <span data-ttu-id="7b7d9-155">Ouvrez une session sur l’ordinateur sur lequel vous exécuterez Lync.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-155">Log on to the computer you’ll be running Lync on.</span></span>

2.  <span data-ttu-id="7b7d9-156">À l’aide d’Internet Explorer, accédez à la page d’inscriptions Web de l’autorité de certification de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-156">Using Internet Explorer, browse to your organization’s Certificate Authority Web Enrollment page.</span></span>
    
    <span data-ttu-id="7b7d9-157">Demandez à votre administrateur Lync Server l’adresse Web de cette ressource si vous ne l’avez pas déjà fait.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-157">Ask your Lync Server administrator for the web address of this resource if you don’t already have it.</span></span> <span data-ttu-id="7b7d9-158">L’URL se présente comme suit : https://MyCA.\[yourcompanyname\]. com/certsrv.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-158">The URL will look something like this: https://MyCA.\[yourcompanyname\].com/certsrv.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7b7d9-159">Si vous utilisez Internet Explorer 10, vous devrez peut-être afficher ce site Web en mode de compatibilité.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-159">If you’re using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

3.  <span data-ttu-id="7b7d9-160">Lorsque vous êtes invité à vous connecter à la page de certification, ouvrez une session à l’aide de votre compte de domaine (plutôt que en tant qu’administrateur de votre ordinateur).</span><span class="sxs-lookup"><span data-stu-id="7b7d9-160">When you’re prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>

4.  <span data-ttu-id="7b7d9-161">Sur la page d’accueil du site Web, sélectionnez **demander un certificat**.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-161">On the website Welcome Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="7b7d9-162">Sélectionnez **demande avancée**.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-162">Select **Advanced Request**.</span></span>

6.  <span data-ttu-id="7b7d9-163">Sélectionnez **créer et envoyer une demande auprès de cette autorité de certification**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-163">Select **Create and submit a request to this CA**, then click **Next**.</span></span>

7.  <span data-ttu-id="7b7d9-164">Vous verrez maintenant une page appelée station d’enregistrement de carte à puce.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-164">Now you’ll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="7b7d9-165">Approuvez la demande d’installation du contrôle ActiveX, puis complétez le formulaire de demande de certificat avancée comme suit :</span><span class="sxs-lookup"><span data-stu-id="7b7d9-165">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    1.  <span data-ttu-id="7b7d9-166">Sélectionnez **utilisateur de carte à puce** dans la liste déroulante **modèle de certificat** .</span><span class="sxs-lookup"><span data-stu-id="7b7d9-166">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    2.  <span data-ttu-id="7b7d9-167">Sélectionnez **créer un nouveau jeu de clés**.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-167">Select **Create new key set**.</span></span>
    
    3.  <span data-ttu-id="7b7d9-168">Recherchez les informations du fabricant sur l’étiquette de votre carte à puce et sélectionnez ce fabricant dans la liste déroulante **CSP** .</span><span class="sxs-lookup"><span data-stu-id="7b7d9-168">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    4.  <span data-ttu-id="7b7d9-169">Sélectionnez **CSP** comme format de demande, s’il n’est pas déjà sélectionné.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-169">Select **CSP** as the Request Format, if it’s not already selected.</span></span>
    
    5.  <span data-ttu-id="7b7d9-170">Sélectionnez **SHA1** dans la liste déroulante algorithme de hachage, si ce n’est déjà fait.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-170">Select **sha1** from the Hash Algorithm dropdown list, if it’s not already selected.</span></span>
    
    6.  <span data-ttu-id="7b7d9-171">Donnez un nom que vous reconnaîtrez à votre certificat, puis cliquez sur **Envoyer**.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-171">Give your certificate a name you’ll recognize, and click **Submit**.</span></span>

8.  <span data-ttu-id="7b7d9-172">À présent, insérez votre carte à puce vierge dans le lecteur de carte connecté à la station d’inscription et cliquez sur **inscrire**.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-172">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

9.  <span data-ttu-id="7b7d9-173">Lorsque vous y êtes invité, entrez votre code confidentiel (PIN), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-173">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7b7d9-174">Si le support technique ne vous a pas fourni de code confidentiel spécial pour inscrire votre carte à puce, utilisez la valeur de code confidentiel par défaut de la carte à puce, qui est 12345678.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-174">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

10. <span data-ttu-id="7b7d9-175">Sélectionnez l’option obliger l’utilisateur (vous) à modifier le code confidentiel la première fois que la carte à puce est utilisée.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-175">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

11. <span data-ttu-id="7b7d9-176">À présent, insérez votre carte à puce vierge dans le lecteur de carte connecté à la station d’inscription et cliquez sur **inscrire**.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-176">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

12. <span data-ttu-id="7b7d9-177">Lorsque vous y êtes invité, entrez votre code confidentiel (PIN), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-177">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7b7d9-178">Si le support technique ne vous a pas fourni de code confidentiel spécial pour inscrire votre carte à puce, utilisez la valeur de code confidentiel par défaut de la carte à puce, qui est 12345678.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-178">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

13. <span data-ttu-id="7b7d9-179">Sélectionnez l’option obliger l’utilisateur (vous) à modifier le code confidentiel la première fois que la carte à puce est utilisée.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-179">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

14. <span data-ttu-id="7b7d9-180">Cliquez sur **OK** pour confirmer que le certificat affiché contient vos informations.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-180">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>

15. <span data-ttu-id="7b7d9-181">Une fois que vous voyez le message indiquant que le certificat a été émis, cliquez sur **installer ce certificat** pour terminer le processus d’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-181">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a><span data-ttu-id="7b7d9-182">Se connecter à Lync avec vos informations d’identification de carte à puce</span><span class="sxs-lookup"><span data-stu-id="7b7d9-182">Sign in to Lync with your smart card credentials</span></span>

<span data-ttu-id="7b7d9-183">Avant d’utiliser votre carte à puce pour la première fois, il est recommandé de cliquer sur **Supprimer mes informations de connexion** sur la page de connexion à Lync.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-183">Before you use your smart card for the first time, it’s recommended that you click **Delete my sign-in info** on the Lync sign-in page.</span></span> <span data-ttu-id="7b7d9-184">Cette opération efface toutes les informations d’identification de connexion stockées sur votre ordinateur et élimine une source d’erreur possible.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-184">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>

<span data-ttu-id="7b7d9-185">**Pour vous connecter à Lync avec vos informations d’identification de carte à puce**</span><span class="sxs-lookup"><span data-stu-id="7b7d9-185">**To sign in to Lync with your smart card credentials**</span></span>

1.  <span data-ttu-id="7b7d9-186">Démarrez le client Lync.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-186">Start the Lync client.</span></span>

2.  <span data-ttu-id="7b7d9-187">Sur l’écran de connexion, tapez votre nom de compte d’utilisateur de connexion dans la zone **adresse de connexion** , puis cliquez sur **se connecter**.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-187">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>

3.  <span data-ttu-id="7b7d9-188">Si vous utilisez une carte à puce virtuelle, ignorez cette étape.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-188">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="7b7d9-189">Si vous utilisez une carte à puce physique, insérez la carte à puce dans votre lecteur de carte à puce et vous y êtes invité, puis cliquez sur **OK** lors de la détection de la carte.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-189">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>

4.  <span data-ttu-id="7b7d9-190">Tapez le code confidentiel de votre carte à puce, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-190">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7b7d9-191">Si vous n’avez pas attribué de numéro de code confidentiel à une carte à puce par votre personne du support technique, utilisez la valeur par défaut, qui est 12345678.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-191">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span>

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

