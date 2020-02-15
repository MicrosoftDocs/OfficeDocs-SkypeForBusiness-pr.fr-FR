---
title: 'Lync Server 2013 : configuration des certificats sur le serveur exécutant la messagerie unifiée Microsoft Exchange Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2885b3610c1edce441c6abbd93a2515fa6cb904
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a><span data-ttu-id="f40eb-102">Configurer des certificats sur le serveur exécutant la messagerie unifiée Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="f40eb-102">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f40eb-103">_**Dernière modification de la rubrique :** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="f40eb-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="f40eb-104">Si vous avez déployé la messagerie unifiée Exchange, comme décrit dans la rubrique [planification de l’intégration de la messagerie unifiée Exchange dans Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) dans la documentation de planification, et que vous souhaitez fournir des fonctionnalités de messagerie unifiée Exchange aux utilisateurs de voix entreprise de votre organisation, vous pouvez utiliser les procédures suivantes pour configurer le certificat sur le serveur exécutant la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="f40eb-104">If you have deployed Exchange Unified Messaging (UM), as described in [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f40eb-105">Pour les certificats internes, les serveurs exécutant Lync Server 2013 et les serveurs exécutant Microsoft Exchange doivent avoir des certificats d’autorité racine approuvés qui sont mutuellement approuvés.</span><span class="sxs-lookup"><span data-stu-id="f40eb-105">For internal certificates, both the servers running Lync Server 2013 and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="f40eb-106">L’autorité de certification (CA) peut être la même ou une autre autorité de certification, tant que le certificat racine de l’autorité de certification est inscrit dans le magasin de certificats de l’autorité racine approuvée.</span><span class="sxs-lookup"><span data-stu-id="f40eb-106">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span>



</div>

<span data-ttu-id="f40eb-107">Le serveur Exchange doit être configuré avec un certificat de serveur afin de se connecter à Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="f40eb-107">The Exchange Server must be configured with a server certificate in order to connect to Lync Server 2013:</span></span>

1.  <span data-ttu-id="f40eb-108">Téléchargez le certificat d’autorité de certification du serveur Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="f40eb-108">Download the CA certificate for the Exchange Server.</span></span>

2.  <span data-ttu-id="f40eb-109">Installez le certificat d’autorité de certification du serveur Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="f40eb-109">Install the CA certificate for the Exchange Server.</span></span>

3.  <span data-ttu-id="f40eb-110">Vérifiez que l’autorité de certification figure dans la liste des autorités de certification racines de confiance du serveur Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="f40eb-110">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>

4.  <span data-ttu-id="f40eb-111">Créez une demande de certificat pour le serveur Exchange Server et installez le certificat.</span><span class="sxs-lookup"><span data-stu-id="f40eb-111">Create a certificate request for the Exchange Server and install the certificate.</span></span>

5.  <span data-ttu-id="f40eb-112">Assignez le certificat du serveur Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="f40eb-112">Assign the certificate for the Exchange Server.</span></span>

<div>

## <a name="to-download-the-ca-certificate"></a><span data-ttu-id="f40eb-113">Pour télécharger le certificat de l’autorité de certification</span><span class="sxs-lookup"><span data-stu-id="f40eb-113">To download the CA certificate</span></span>

1.  <span data-ttu-id="f40eb-114">Sur le serveur exécutant la messagerie unifiée Exchange, cliquez sur **Démarrer**, sur **exécuter**, tapez **http://\<nom de\>votre autorité de certification serveur/certsrv**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-114">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="f40eb-115">Sous **Sélectionnez une tâche**, cliquez sur **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou la liste de révocation de certificats**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-115">Under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

3.  <span data-ttu-id="f40eb-116">Sous **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou une liste de révocation**de certificats, sélectionnez **méthode de codage pour baser 64**, puis cliquez sur Télécharger le certificat de l' **autorité de certification**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-116">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f40eb-117">Vous pouvez également spécifier le codage DER (Distinguished Encoding Rules) à cette étape.</span><span class="sxs-lookup"><span data-stu-id="f40eb-117">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="f40eb-118">Si vous sélectionnez cette méthode, le fichier spécifié à l’étape suivante de cette procédure et à l’étape 10 de la procédure <STRONG>Pour installer le certificat de l’autorité de certification</STRONG> sera de type .p7b et non .cer.</span><span class="sxs-lookup"><span data-stu-id="f40eb-118">If you select DER encoding, the file type in the next step of this procedure and in step 10 of <STRONG>To Install the CA certificate</STRONG> is .p7b rather than .cer.</span></span>

    
    </div>

4.  <span data-ttu-id="f40eb-p103">Dans la boîte de dialogue **Téléchargement de fichier**, cliquez sur **Enregistrer**, puis enregistrez le fichier sur le disque dur du serveur (le fichier sera doté de l’extension .cer ou .p7b, selon la méthode de codage que vous avez sélectionnée à l’étape précédente).</span><span class="sxs-lookup"><span data-stu-id="f40eb-p103">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

</div>

<div>

## <a name="to-install-the-ca-certificate"></a><span data-ttu-id="f40eb-121">Pour installer le certificat de l’autorité de certification</span><span class="sxs-lookup"><span data-stu-id="f40eb-121">To install the CA certificate</span></span>

1.  <span data-ttu-id="f40eb-122">Sur le serveur exécutant la messagerie unifiée Exchange, ouvrez la console MMC (Microsoft Management Console) en cliquant sur **Démarrer**, sur **exécuter**, en tapant **MMC** dans la zone **ouvrir** , puis en cliquant sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-122">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="f40eb-123">Dans le menu **Fichier**, cliquez sur **Ajouter/Supprimer un composant logiciel enfichable**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-123">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="f40eb-124">Dans la zone **Ajout d’un composant logiciel enfichable autonome**, cliquez sur **Certificats**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-124">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="f40eb-125">Dans la boîte de dialogue **Composant logiciel enfichable Certificats**, cliquez sur **Compte d’ordinateur**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-125">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="f40eb-126">Dans la boîte de dialogue **Sélectionner un ordinateur** , vérifiez que la case à cocher **ordinateur local : (l’ordinateur sur lequel cette console s’exécute)** est activée, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-126">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="f40eb-127">Cliquez sur **Fermer**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-127">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="f40eb-128">Dans l’arborescence de la console, développez **Certificats (ordinateur local)**, développez **Autorités de certification racines de confiance**, puis cliquez sur **Certificats**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-128">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

8.  <span data-ttu-id="f40eb-129">Cliquez avec le bouton droit sur **Certificats**, cliquez sur **Toutes les tâches**, puis sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-129">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>

9.  <span data-ttu-id="f40eb-130">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-130">Click **Next**.</span></span>

10. <span data-ttu-id="f40eb-p104">Cliquez sur **Parcourir** pour localiser le fichier, puis cliquez sur **Suivant**. Le fichier sera doté de l’extension .cer ou .p7b, selon la méthode de codage sélectionnée à l’étape 3 de la procédure **Pour télécharger le certificat de l’autorité de certification**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-p104">Click **Browse** to locate the file, and then click **Next**. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>

11. <span data-ttu-id="f40eb-133">Cliquez sur **Placer tous les certificats dans le magasin suivant**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-133">Click **Place All Certificates in the following store**.</span></span>

12. <span data-ttu-id="f40eb-134">Cliquez sur **Parcourir**, puis sélectionnez **Autorités de certification racines de confiance**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-134">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span>

13. <span data-ttu-id="f40eb-135">Cliquez sur **Suivant** pour vérifier les paramètres, puis sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-135">Click **Next** to verify the settings, and then click **Finish**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a><span data-ttu-id="f40eb-136">Pour vérifier que l’autorité de certification figure sur la liste des autorités de certification racines de confiance</span><span class="sxs-lookup"><span data-stu-id="f40eb-136">To verify that the CA is in the list of trusted root CAs</span></span>

1.  <span data-ttu-id="f40eb-137">Sur le serveur exécutant la messagerie unifiée Exchange, dans la console MMC, développez **certificats (ordinateur local)**, développez **autorités de certification racines de confiance**, puis cliquez sur **certificats**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-137">On the server running Exchange UM, in MMC expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

2.  <span data-ttu-id="f40eb-138">Dans le volet de détail, vérifiez que votre autorité de certification figure sur la liste des autorités de certification de confiance.</span><span class="sxs-lookup"><span data-stu-id="f40eb-138">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a><span data-ttu-id="f40eb-139">Pour configurer la messagerie unifiée Exchange Server 2013 avec Lync Server</span><span class="sxs-lookup"><span data-stu-id="f40eb-139">To configure Exchange Server 2013 UM with Lync Server</span></span>

1.  <span data-ttu-id="f40eb-140">Pour plus d’informations, voir « intégration de la messagerie unifiée Exchange 2013 avec Lync Server » [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)dans la documentation d’Exchange Server à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="f40eb-140">For details, see "Integrate Exchange 2013 UM with Lync Server" in the Exchange Server documentation at [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="f40eb-141">Pour créer une demande de certificat et installer le certificat sur Exchange Server 2007 (SP1)</span><span class="sxs-lookup"><span data-stu-id="f40eb-141">To create a certificate request and install the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="f40eb-142">Sur le serveur exécutant la messagerie unifiée Exchange, cliquez sur **Démarrer**, sur **exécuter**, tapez **\<http://** nom de votre autorité de certification serveur**\>/certsrv**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-142">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<** name of your Issuing CA Server**\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="f40eb-143">Sous **Sélectionner une tâche**, cliquez sur **Demander un certificat**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-143">Under **Select a task**, click **Request a Certificate**.</span></span>

3.  <span data-ttu-id="f40eb-144">Sous **Demander un certificat**, cliquez sur **Demande de certificat avancée**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-144">Under **Request a Certificate**, click **Advanced certificate request**.</span></span>

4.  <span data-ttu-id="f40eb-145">Sous **Demande de certificat avancée**, cliquez sur **Créer et soumettre une demande de certification auprès de cette Autorité de certification**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-145">Under **Advanced Certificate Request**, click **Create and submit a request to this CA**.</span></span>

5.  <span data-ttu-id="f40eb-146">Sous **Demande de certificat avancée**, sélectionnez **Serveur web** ou un autre modèle de certificat du serveur configuré pour l’authentification du serveur.</span><span class="sxs-lookup"><span data-stu-id="f40eb-146">Under **Advanced Certificate Request**, select **Web server** or another server certificate template configured for server authentication.</span></span>

6.  <span data-ttu-id="f40eb-147">Sous **informations d’identification pour le modèle hors connexion**, dans la zone **nom** , tapez le nom de domaine complet (FQDN) du serveur Exchange.</span><span class="sxs-lookup"><span data-stu-id="f40eb-147">Under **Identifying Information for Offline Template**, in the **Name** box, type the fully qualified domain name (FQDN) of the Exchange Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f40eb-148">Vous devez entrer le nom de domaine complet du serveur Exchange Server pour que les communications fonctionnent.</span><span class="sxs-lookup"><span data-stu-id="f40eb-148">You must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

7.  <span data-ttu-id="f40eb-149">Sous **Options de la clé**, activez la case à cocher **Stocker le certificat dans le magasin de certificats de l’ordinateur local**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-149">Under **Key Options**, click the **Store certificate in the local computer certificate store** check box.</span></span>

8.  <span data-ttu-id="f40eb-150">Cliquez sur le bouton **Envoyer** en bas de la page web.</span><span class="sxs-lookup"><span data-stu-id="f40eb-150">Click the **Submit** button in the bottom of the webpage.</span></span>

9.  <span data-ttu-id="f40eb-151">Dans la boîte de dialogue de confirmation qui s’affiche, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-151">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

10. <span data-ttu-id="f40eb-152">Dans la page Certificat émis, sous **Certificat émis**, cliquez sur **Installer ce certificat**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-152">On the Certificate Issued page, under **Certificate Issued**, click **Install this certificate**.</span></span>

11. <span data-ttu-id="f40eb-153">Dans la boîte de dialogue de confirmation qui s’affiche, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-153">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

12. <span data-ttu-id="f40eb-154">Vérifiez que le message « Votre nouveau certificat a été correctement installé » s’affiche.</span><span class="sxs-lookup"><span data-stu-id="f40eb-154">Verify that the message "Your new certificate has been successfully installed" appears.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a><span data-ttu-id="f40eb-155">Pour créer un certificat sur Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="f40eb-155">To create a certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="f40eb-156">Ouvrez une session sur le serveur exécutant la messagerie unifiée Exchange avec les droits d’utilisateur appropriés.</span><span class="sxs-lookup"><span data-stu-id="f40eb-156">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="f40eb-157">Pour plus d’informations, voir « autorisations d’accès [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)au client » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="f40eb-157">For details, see "Client Access Permissions" at [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="f40eb-158">Suivez les procédures ci-après pour créer le certificat :</span><span class="sxs-lookup"><span data-stu-id="f40eb-158">Refer to the following procedures to create the certificate:</span></span>
    
    1.  <span data-ttu-id="f40eb-159">« Créer un nouveau certificat Exchange » à l’adresse[http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)</span><span class="sxs-lookup"><span data-stu-id="f40eb-159">"Create a New Exchange Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)</span></span>
    
    2.  <span data-ttu-id="f40eb-160">« Importer un certificat Exchange » à l’adresse[http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)</span><span class="sxs-lookup"><span data-stu-id="f40eb-160">"Import an Exchange Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f40eb-161">Pour le <STRONG>Nom du sujet</STRONG> du certificat, vous devez entrer le nom de domaine complet du serveur Exchange Server pour que les communications fonctionnent.</span><span class="sxs-lookup"><span data-stu-id="f40eb-161">For the certificate <STRONG>Subject Name</STRONG>, you must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="f40eb-162">Pour attribuer le certificat au serveur Exchange Server 2007 (SP1)</span><span class="sxs-lookup"><span data-stu-id="f40eb-162">To assign the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="f40eb-163">Sur le serveur exécutant la messagerie unifiée Exchange, ouvrez la console MMC.</span><span class="sxs-lookup"><span data-stu-id="f40eb-163">On the server running Exchange UM, open MMC.</span></span>

2.  <span data-ttu-id="f40eb-164">Dans l’arborescence de la console, développez **Personnel** puis cliquez sur **Certificats**.</span><span class="sxs-lookup"><span data-stu-id="f40eb-164">In the console tree, expand **Personal** and then click **Certificates**.</span></span>

3.  <span data-ttu-id="f40eb-165">Dans le volet de détail, vérifiez que le certificat personnel est bien affiché.</span><span class="sxs-lookup"><span data-stu-id="f40eb-165">In the details pane, verify that personal certificate is displayed.</span></span>

4.  <span data-ttu-id="f40eb-166">Double-cliquez sur le certificat pour lire ses détails et vérifier qu’il est valide.</span><span class="sxs-lookup"><span data-stu-id="f40eb-166">Double-click the certificate to read its details and verify that it is valid.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f40eb-167">Cela peut prendre quelques minutes avant que le certificat s’affiche comme étant valide.</span><span class="sxs-lookup"><span data-stu-id="f40eb-167">It may take a few minutes before the certificate displays as valid.</span></span>

    
    </div>

5.  <span data-ttu-id="f40eb-168">Redémarrez le service de messagerie unifiée Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="f40eb-168">Restart the Microsoft Exchange Unified Messaging service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f40eb-169">Le serveur qui exécute la messagerie unifiée Exchange Server 2007 SP1 récupère automatiquement le bon certificat.</span><span class="sxs-lookup"><span data-stu-id="f40eb-169">The server running Exchange Server 2007 SP1 Unified Messaging automatically retrieves the correct certificate.</span></span>

    
    </div>

6.  <span data-ttu-id="f40eb-170">Ouvrez l’Observateur d’événements et recherchez l’ID de l’événement 1112. Il indique le certificat récupéré par le serveur exécutant la messagerie unifiée Exchange Server 2007 SP1.</span><span class="sxs-lookup"><span data-stu-id="f40eb-170">Open Event Viewer and look for Event ID 1112, which specifies what certificate the server running Exchange Server 2007 SP1 Unified Messaging has retrieved.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a><span data-ttu-id="f40eb-171">Pour attribuer le certificat au serveur Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="f40eb-171">To assign the certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="f40eb-172">Ouvrez une session sur le serveur exécutant la messagerie unifiée Exchange avec les droits d’utilisateur appropriés.</span><span class="sxs-lookup"><span data-stu-id="f40eb-172">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="f40eb-173">Pour plus d’informations, voir « autorisations d’accès [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)au client » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="f40eb-173">For details, see "Client Access Permissions" at [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="f40eb-174">Pour obtenir la procédure d’attribution du certificat, consultez la rubrique « attribuer des services à [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497)un certificat » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="f40eb-174">For the procedure to assign the certificate, see "Assign Services to a Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

