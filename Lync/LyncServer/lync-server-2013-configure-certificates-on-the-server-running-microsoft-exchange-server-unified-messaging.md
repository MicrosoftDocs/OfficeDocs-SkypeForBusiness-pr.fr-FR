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
ms.openlocfilehash: 790798835694fcd76a4501c4b94e6ca59f220524
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521041"
---
# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a><span data-ttu-id="6497b-102">Configurer des certificats sur le serveur exécutant la messagerie unifiée Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="6497b-102">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6497b-103">_**Dernière modification de la rubrique :** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="6497b-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="6497b-104">Si vous avez déployé la messagerie unifiée Exchange, comme décrit dans la rubrique [planification de l’intégration de la messagerie unifiée Exchange dans Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) dans la documentation de planification, et que vous souhaitez fournir des fonctionnalités de messagerie unifiée Exchange aux utilisateurs de voix entreprise de votre organisation, vous pouvez utiliser les procédures suivantes pour configurer le certificat sur le serveur exécutant la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="6497b-104">If you have deployed Exchange Unified Messaging (UM), as described in [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6497b-105">Pour les certificats internes, les serveurs exécutant Lync Server 2013 et les serveurs exécutant Microsoft Exchange doivent avoir des certificats d’autorité racine approuvés qui sont mutuellement approuvés.</span><span class="sxs-lookup"><span data-stu-id="6497b-105">For internal certificates, both the servers running Lync Server 2013 and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="6497b-106">L’autorité de certification (CA) peut être la même ou une autre autorité de certification, tant que le certificat racine de l’autorité de certification est inscrit dans le magasin de certificats de l’autorité racine approuvée.</span><span class="sxs-lookup"><span data-stu-id="6497b-106">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span>



</div>

<span data-ttu-id="6497b-107">Le serveur Exchange doit être configuré avec un certificat de serveur afin de se connecter à Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="6497b-107">The Exchange Server must be configured with a server certificate in order to connect to Lync Server 2013:</span></span>

1.  <span data-ttu-id="6497b-108">Téléchargez le certificat d’autorité de certification du serveur Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="6497b-108">Download the CA certificate for the Exchange Server.</span></span>

2.  <span data-ttu-id="6497b-109">Installez le certificat d’autorité de certification du serveur Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="6497b-109">Install the CA certificate for the Exchange Server.</span></span>

3.  <span data-ttu-id="6497b-110">Vérifiez que l’autorité de certification figure dans la liste des autorités de certification racines de confiance du serveur Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="6497b-110">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>

4.  <span data-ttu-id="6497b-111">Créez une demande de certificat pour le serveur Exchange Server et installez le certificat.</span><span class="sxs-lookup"><span data-stu-id="6497b-111">Create a certificate request for the Exchange Server and install the certificate.</span></span>

5.  <span data-ttu-id="6497b-112">Assignez le certificat du serveur Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="6497b-112">Assign the certificate for the Exchange Server.</span></span>

<div>

## <a name="to-download-the-ca-certificate"></a><span data-ttu-id="6497b-113">Pour télécharger le certificat de l’autorité de certification</span><span class="sxs-lookup"><span data-stu-id="6497b-113">To download the CA certificate</span></span>

1.  <span data-ttu-id="6497b-114">Sur le serveur exécutant la messagerie unifiée Exchange, cliquez sur **Démarrer**, sur **exécuter**, tapez **http:// \<name of your Issuing CA Server\> /certsrv**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6497b-114">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="6497b-115">Sous **Sélectionnez une tâche**, cliquez sur **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou la liste de révocation de certificats**.</span><span class="sxs-lookup"><span data-stu-id="6497b-115">Under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

3.  <span data-ttu-id="6497b-116">Sous **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou une liste de révocation**de certificats, sélectionnez **méthode de codage pour baser 64**, puis cliquez sur Télécharger le certificat de l' **autorité de certification**.</span><span class="sxs-lookup"><span data-stu-id="6497b-116">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6497b-117">Vous pouvez également spécifier le codage DER (Distinguished Encoding Rules) à cette étape.</span><span class="sxs-lookup"><span data-stu-id="6497b-117">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="6497b-118">Si vous sélectionnez cette méthode, le fichier spécifié à l’étape suivante de cette procédure et à l’étape 10 de la procédure <STRONG>Pour installer le certificat de l’autorité de certification</STRONG> sera de type .p7b et non .cer.</span><span class="sxs-lookup"><span data-stu-id="6497b-118">If you select DER encoding, the file type in the next step of this procedure and in step 10 of <STRONG>To Install the CA certificate</STRONG> is .p7b rather than .cer.</span></span>

    
    </div>

4.  <span data-ttu-id="6497b-p103">Dans la boîte de dialogue **Téléchargement de fichier**, cliquez sur **Enregistrer**, puis enregistrez le fichier sur le disque dur du serveur (le fichier sera doté de l’extension .cer ou .p7b, selon la méthode de codage que vous avez sélectionnée à l’étape précédente).</span><span class="sxs-lookup"><span data-stu-id="6497b-p103">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

</div>

<div>

## <a name="to-install-the-ca-certificate"></a><span data-ttu-id="6497b-121">Pour installer le certificat de l’autorité de certification</span><span class="sxs-lookup"><span data-stu-id="6497b-121">To install the CA certificate</span></span>

1.  <span data-ttu-id="6497b-122">Sur le serveur exécutant la messagerie unifiée Exchange, ouvrez la console MMC (Microsoft Management Console) en cliquant sur **Démarrer**, sur **exécuter**, en tapant **MMC** dans la zone **ouvrir** , puis en cliquant sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6497b-122">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="6497b-123">Dans le menu **Fichier**, cliquez sur **Ajouter/Supprimer un composant logiciel enfichable**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="6497b-123">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="6497b-124">Dans la zone **Ajout d’un composant logiciel enfichable autonome**, cliquez sur **Certificats**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="6497b-124">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="6497b-125">Dans la boîte de dialogue **Composant logiciel enfichable Certificats**, cliquez sur **Compte d’ordinateur**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="6497b-125">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="6497b-126">Dans la boîte de dialogue **Sélectionner un ordinateur** , vérifiez que la case à cocher **ordinateur local : (l’ordinateur sur lequel cette console s’exécute)** est activée, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="6497b-126">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="6497b-127">Cliquez sur **Fermer**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6497b-127">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="6497b-128">Dans l’arborescence de la console, développez **Certificats (ordinateur local)**, développez **Autorités de certification racines de confiance**, puis cliquez sur **Certificats**.</span><span class="sxs-lookup"><span data-stu-id="6497b-128">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

8.  <span data-ttu-id="6497b-129">Cliquez avec le bouton droit sur **Certificats**, cliquez sur **Toutes les tâches**, puis sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="6497b-129">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>

9.  <span data-ttu-id="6497b-130">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="6497b-130">Click **Next**.</span></span>

10. <span data-ttu-id="6497b-p104">Cliquez sur **Parcourir** pour localiser le fichier, puis cliquez sur **Suivant**. Le fichier sera doté de l’extension .cer ou .p7b, selon la méthode de codage sélectionnée à l’étape 3 de la procédure **Pour télécharger le certificat de l’autorité de certification**.</span><span class="sxs-lookup"><span data-stu-id="6497b-p104">Click **Browse** to locate the file, and then click **Next**. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>

11. <span data-ttu-id="6497b-133">Cliquez sur **Placer tous les certificats dans le magasin suivant**.</span><span class="sxs-lookup"><span data-stu-id="6497b-133">Click **Place All Certificates in the following store**.</span></span>

12. <span data-ttu-id="6497b-134">Cliquez sur **Parcourir**, puis sélectionnez **Autorités de certification racines de confiance**.</span><span class="sxs-lookup"><span data-stu-id="6497b-134">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span>

13. <span data-ttu-id="6497b-135">Cliquez sur **Suivant** pour vérifier les paramètres, puis sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="6497b-135">Click **Next** to verify the settings, and then click **Finish**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a><span data-ttu-id="6497b-136">Pour vérifier que l’autorité de certification figure sur la liste des autorités de certification racines de confiance</span><span class="sxs-lookup"><span data-stu-id="6497b-136">To verify that the CA is in the list of trusted root CAs</span></span>

1.  <span data-ttu-id="6497b-137">Sur le serveur exécutant la messagerie unifiée Exchange, dans la console MMC, développez **certificats (ordinateur local)**, développez **autorités de certification racines de confiance**, puis cliquez sur **certificats**.</span><span class="sxs-lookup"><span data-stu-id="6497b-137">On the server running Exchange UM, in MMC expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

2.  <span data-ttu-id="6497b-138">Dans le volet de détail, vérifiez que votre autorité de certification figure sur la liste des autorités de certification de confiance.</span><span class="sxs-lookup"><span data-stu-id="6497b-138">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a><span data-ttu-id="6497b-139">Pour configurer la messagerie unifiée Exchange Server 2013 avec Lync Server</span><span class="sxs-lookup"><span data-stu-id="6497b-139">To configure Exchange Server 2013 UM with Lync Server</span></span>

1.  <span data-ttu-id="6497b-140">Pour plus d’informations, voir « intégration de la messagerie unifiée Exchange 2013 avec Lync Server » dans la documentation d’Exchange Server à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372) .</span><span class="sxs-lookup"><span data-stu-id="6497b-140">For details, see "Integrate Exchange 2013 UM with Lync Server" in the Exchange Server documentation at [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="6497b-141">Pour créer une demande de certificat et installer le certificat sur Exchange Server 2007 (SP1)</span><span class="sxs-lookup"><span data-stu-id="6497b-141">To create a certificate request and install the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="6497b-142">Sur le serveur exécutant la messagerie unifiée Exchange, cliquez sur **Démarrer**, sur **exécuter**, tapez **http:// \<**name of your Issuing CA Server**\> /certsrv**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6497b-142">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<**name of your Issuing CA Server**\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="6497b-143">Sous **Sélectionner une tâche**, cliquez sur **Demander un certificat**.</span><span class="sxs-lookup"><span data-stu-id="6497b-143">Under **Select a task**, click **Request a Certificate**.</span></span>

3.  <span data-ttu-id="6497b-144">Sous **Demander un certificat**, cliquez sur **Demande de certificat avancée**.</span><span class="sxs-lookup"><span data-stu-id="6497b-144">Under **Request a Certificate**, click **Advanced certificate request**.</span></span>

4.  <span data-ttu-id="6497b-145">Sous **Demande de certificat avancée**, cliquez sur **Créer et soumettre une demande de certification auprès de cette Autorité de certification**.</span><span class="sxs-lookup"><span data-stu-id="6497b-145">Under **Advanced Certificate Request**, click **Create and submit a request to this CA**.</span></span>

5.  <span data-ttu-id="6497b-146">Sous **Demande de certificat avancée**, sélectionnez **Serveur web** ou un autre modèle de certificat du serveur configuré pour l’authentification du serveur.</span><span class="sxs-lookup"><span data-stu-id="6497b-146">Under **Advanced Certificate Request**, select **Web server** or another server certificate template configured for server authentication.</span></span>

6.  <span data-ttu-id="6497b-147">Sous **informations d’identification pour le modèle hors connexion**, dans la zone **nom** , tapez le nom de domaine complet (FQDN) du serveur Exchange.</span><span class="sxs-lookup"><span data-stu-id="6497b-147">Under **Identifying Information for Offline Template**, in the **Name** box, type the fully qualified domain name (FQDN) of the Exchange Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6497b-148">Vous devez entrer le nom de domaine complet du serveur Exchange Server pour que les communications fonctionnent.</span><span class="sxs-lookup"><span data-stu-id="6497b-148">You must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

7.  <span data-ttu-id="6497b-149">Sous **Options de la clé**, activez la case à cocher **Stocker le certificat dans le magasin de certificats de l’ordinateur local**.</span><span class="sxs-lookup"><span data-stu-id="6497b-149">Under **Key Options**, click the **Store certificate in the local computer certificate store** check box.</span></span>

8.  <span data-ttu-id="6497b-150">Cliquez sur le bouton **Envoyer** en bas de la page web.</span><span class="sxs-lookup"><span data-stu-id="6497b-150">Click the **Submit** button in the bottom of the webpage.</span></span>

9.  <span data-ttu-id="6497b-151">Dans la boîte de dialogue de confirmation qui s’affiche, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="6497b-151">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

10. <span data-ttu-id="6497b-152">Dans la page Certificat émis, sous **Certificat émis**, cliquez sur **Installer ce certificat**.</span><span class="sxs-lookup"><span data-stu-id="6497b-152">On the Certificate Issued page, under **Certificate Issued**, click **Install this certificate**.</span></span>

11. <span data-ttu-id="6497b-153">Dans la boîte de dialogue de confirmation qui s’affiche, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="6497b-153">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

12. <span data-ttu-id="6497b-154">Vérifiez que le message « Votre nouveau certificat a été correctement installé » s’affiche.</span><span class="sxs-lookup"><span data-stu-id="6497b-154">Verify that the message "Your new certificate has been successfully installed" appears.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a><span data-ttu-id="6497b-155">Pour créer un certificat sur Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="6497b-155">To create a certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="6497b-156">Ouvrez une session sur le serveur exécutant la messagerie unifiée Exchange avec les droits d’utilisateur appropriés.</span><span class="sxs-lookup"><span data-stu-id="6497b-156">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="6497b-157">Pour plus d’informations, voir « autorisations d’accès au client » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499) .</span><span class="sxs-lookup"><span data-stu-id="6497b-157">For details, see "Client Access Permissions" at [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="6497b-158">Suivez les procédures ci-après pour créer le certificat :</span><span class="sxs-lookup"><span data-stu-id="6497b-158">Refer to the following procedures to create the certificate:</span></span>
    
    1.  <span data-ttu-id="6497b-159">« Créer un nouveau certificat Exchange » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)</span><span class="sxs-lookup"><span data-stu-id="6497b-159">"Create a New Exchange Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)</span></span>
    
    2.  <span data-ttu-id="6497b-160">« Importer un certificat Exchange » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)</span><span class="sxs-lookup"><span data-stu-id="6497b-160">"Import an Exchange Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6497b-161">Pour le <STRONG>Nom du sujet</STRONG> du certificat, vous devez entrer le nom de domaine complet du serveur Exchange Server pour que les communications fonctionnent.</span><span class="sxs-lookup"><span data-stu-id="6497b-161">For the certificate <STRONG>Subject Name</STRONG>, you must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="6497b-162">Pour attribuer le certificat au serveur Exchange Server 2007 (SP1)</span><span class="sxs-lookup"><span data-stu-id="6497b-162">To assign the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="6497b-163">Sur le serveur exécutant la messagerie unifiée Exchange, ouvrez la console MMC.</span><span class="sxs-lookup"><span data-stu-id="6497b-163">On the server running Exchange UM, open MMC.</span></span>

2.  <span data-ttu-id="6497b-164">Dans l’arborescence de la console, développez **Personnel** puis cliquez sur **Certificats**.</span><span class="sxs-lookup"><span data-stu-id="6497b-164">In the console tree, expand **Personal** and then click **Certificates**.</span></span>

3.  <span data-ttu-id="6497b-165">Dans le volet de détail, vérifiez que le certificat personnel est bien affiché.</span><span class="sxs-lookup"><span data-stu-id="6497b-165">In the details pane, verify that personal certificate is displayed.</span></span>

4.  <span data-ttu-id="6497b-166">Double-cliquez sur le certificat pour lire ses détails et vérifier qu’il est valide.</span><span class="sxs-lookup"><span data-stu-id="6497b-166">Double-click the certificate to read its details and verify that it is valid.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6497b-167">Cela peut prendre quelques minutes avant que le certificat s’affiche comme étant valide.</span><span class="sxs-lookup"><span data-stu-id="6497b-167">It may take a few minutes before the certificate displays as valid.</span></span>

    
    </div>

5.  <span data-ttu-id="6497b-168">Redémarrez le service de messagerie unifiée Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="6497b-168">Restart the Microsoft Exchange Unified Messaging service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6497b-169">Le serveur qui exécute la messagerie unifiée Exchange Server 2007 SP1 récupère automatiquement le bon certificat.</span><span class="sxs-lookup"><span data-stu-id="6497b-169">The server running Exchange Server 2007 SP1 Unified Messaging automatically retrieves the correct certificate.</span></span>

    
    </div>

6.  <span data-ttu-id="6497b-170">Ouvrez l’Observateur d’événements et recherchez l’ID de l’événement 1112. Il indique le certificat récupéré par le serveur exécutant la messagerie unifiée Exchange Server 2007 SP1.</span><span class="sxs-lookup"><span data-stu-id="6497b-170">Open Event Viewer and look for Event ID 1112, which specifies what certificate the server running Exchange Server 2007 SP1 Unified Messaging has retrieved.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a><span data-ttu-id="6497b-171">Pour attribuer le certificat au serveur Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="6497b-171">To assign the certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="6497b-172">Ouvrez une session sur le serveur exécutant la messagerie unifiée Exchange avec les droits d’utilisateur appropriés.</span><span class="sxs-lookup"><span data-stu-id="6497b-172">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="6497b-173">Pour plus d’informations, voir « autorisations d’accès au client » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499) .</span><span class="sxs-lookup"><span data-stu-id="6497b-173">For details, see "Client Access Permissions" at [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="6497b-174">Pour obtenir la procédure d’attribution du certificat, consultez la rubrique « attribuer des services à un certificat » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497) .</span><span class="sxs-lookup"><span data-stu-id="6497b-174">For the procedure to assign the certificate, see "Assign Services to a Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

