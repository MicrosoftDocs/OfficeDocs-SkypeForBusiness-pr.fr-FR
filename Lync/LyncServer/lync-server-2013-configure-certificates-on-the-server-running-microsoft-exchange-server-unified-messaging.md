---
title: 'Lync Server 2013 : configurer des certificats sur le serveur exécutant la messagerie unifiée Microsoft Exchange Server'
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
ms.openlocfilehash: 6d31ed8b750d0162a2c09d49ca8a350731896086
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a><span data-ttu-id="f0c55-102">Configurer des certificats sur le serveur exécutant la messagerie unifiée Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="f0c55-102">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0c55-103">_**Dernière modification de la rubrique :** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="f0c55-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="f0c55-104">Si vous avez déployé la messagerie unifiée Exchange, comme décrit dans la section [planification de l’intégration de la messagerie unifiée Exchange dans Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) dans la documentation de planification, et si vous souhaitez fournir des fonctionnalités de messagerie unifiée Exchange aux utilisateurs d’entreprise Voice au sein de votre organisation, vous pouvez utiliser les procédures suivantes pour configurer le certificat sur le serveur exécutant la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="f0c55-104">If you have deployed Exchange Unified Messaging (UM), as described in [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f0c55-105">Pour les certificats internes, les serveurs exécutant Lync Server 2013 et les serveurs exécutant Microsoft Exchange doivent disposer de certificats d’autorité racine approuvés qui sont mutuellement approuvés.</span><span class="sxs-lookup"><span data-stu-id="f0c55-105">For internal certificates, both the servers running Lync Server 2013 and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="f0c55-106">L’autorité de certification (CA) peut être le même, ou une autre autorité de certification, tant que le certificat racine de l’autorité de certification est inscrit sur les serveurs dans leur magasin de certificats.</span><span class="sxs-lookup"><span data-stu-id="f0c55-106">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span>



</div>

<span data-ttu-id="f0c55-107">Le serveur Exchange doit être configuré avec un certificat de serveur pour pouvoir se connecter à Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="f0c55-107">The Exchange Server must be configured with a server certificate in order to connect to Lync Server 2013:</span></span>

1.  <span data-ttu-id="f0c55-108">Téléchargez le certificat d’autorité de certification du serveur Exchange.</span><span class="sxs-lookup"><span data-stu-id="f0c55-108">Download the CA certificate for the Exchange Server.</span></span>

2.  <span data-ttu-id="f0c55-109">Installez le certificat d’autorité de certification du serveur Exchange.</span><span class="sxs-lookup"><span data-stu-id="f0c55-109">Install the CA certificate for the Exchange Server.</span></span>

3.  <span data-ttu-id="f0c55-110">Vérifiez que la CA figure dans la liste des autorités de certification racines de confiance du serveur Exchange.</span><span class="sxs-lookup"><span data-stu-id="f0c55-110">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>

4.  <span data-ttu-id="f0c55-111">Créez une demande de certificat pour le serveur Exchange et installez le certificat.</span><span class="sxs-lookup"><span data-stu-id="f0c55-111">Create a certificate request for the Exchange Server and install the certificate.</span></span>

5.  <span data-ttu-id="f0c55-112">Attribuez le certificat du serveur Exchange.</span><span class="sxs-lookup"><span data-stu-id="f0c55-112">Assign the certificate for the Exchange Server.</span></span>

<div>

## <a name="to-download-the-ca-certificate"></a><span data-ttu-id="f0c55-113">Pour télécharger le certificat d’autorité de certification</span><span class="sxs-lookup"><span data-stu-id="f0c55-113">To download the CA certificate</span></span>

1.  <span data-ttu-id="f0c55-114">Sur le serveur exécutant la messagerie unifiée Exchange, cliquez sur **Démarrer**, sur **exécuter**, tapez **le nom\<http://\>de votre serveur de certification émettrice/certsrv**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-114">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="f0c55-115">Sous **Sélectionner une tâche**, cliquez sur **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou une LRC**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-115">Under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

3.  <span data-ttu-id="f0c55-116">Sous **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou une LRC**, sélectionnez **méthode d’encodage pour baser 64**, puis cliquez sur **Télécharger le certificat d’autorité de certification**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-116">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f0c55-117">Vous pouvez également spécifier le codage DER (Distinguished Encoding Rules) à cette étape.</span><span class="sxs-lookup"><span data-stu-id="f0c55-117">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="f0c55-118">Si vous sélectionnez DER Encoding, le type de fichier à l’étape suivante de cette procédure et à l’étape 10 de <STRONG>pour installer le certificat d’autorité de certification</STRONG> est. p7b plutôt que. cer.</span><span class="sxs-lookup"><span data-stu-id="f0c55-118">If you select DER encoding, the file type in the next step of this procedure and in step 10 of <STRONG>To Install the CA certificate</STRONG> is .p7b rather than .cer.</span></span>

    
    </div>

4.  <span data-ttu-id="f0c55-119">Dans la boîte de dialogue **téléchargement de fichier** , cliquez sur **Enregistrer**, puis enregistrez le fichier sur le disque dur sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="f0c55-119">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server.</span></span> <span data-ttu-id="f0c55-120">(Le fichier aura une extension de fichier. cer ou. p7b, selon le codage que vous avez sélectionné à l’étape précédente.)</span><span class="sxs-lookup"><span data-stu-id="f0c55-120">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

</div>

<div>

## <a name="to-install-the-ca-certificate"></a><span data-ttu-id="f0c55-121">Pour installer le certificat d’autorité de certification</span><span class="sxs-lookup"><span data-stu-id="f0c55-121">To install the CA certificate</span></span>

1.  <span data-ttu-id="f0c55-122">Sur le serveur exécutant Exchange UM, ouvrez Microsoft Management Console (MMC) en cliquant **sur Démarrer**, sur **exécuter**, en tapant **MMC** dans la zone **ouvrir** , puis en cliquant sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-122">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="f0c55-123">Dans le menu **fichier** , cliquez sur **Ajouter/supprimer un composant logiciel enfichable**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-123">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="f0c55-124">Dans la boîte de dialogue **Ajouter des composants logiciels enfichables autonomes** , cliquez sur **certificats**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-124">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="f0c55-125">Dans la boîte de dialogue **Composant logiciel enfichable Certificats**, cliquez sur **Compte d’ordinateur**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-125">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="f0c55-126">Dans la boîte de dialogue **Sélectionner un ordinateur** , vérifiez que la case à cocher **ordinateur local : (l’ordinateur sur lequel cette console s’exécute)** est activée, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-126">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="f0c55-127">Cliquez sur **Fermer**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-127">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="f0c55-128">Dans l’arborescence de la console, développez **certificats (ordinateur local)**, développez **autorités de certification racine de confiance**, puis cliquez sur **certificats**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-128">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

8.  <span data-ttu-id="f0c55-129">Cliquez avec le bouton droit sur **certificats**, puis cliquez sur **toutes les tâches**et sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-129">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>

9.  <span data-ttu-id="f0c55-130">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-130">Click **Next**.</span></span>

10. <span data-ttu-id="f0c55-131">Cliquez sur **Parcourir** pour rechercher le fichier, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-131">Click **Browse** to locate the file, and then click **Next**.</span></span> <span data-ttu-id="f0c55-132">(Le fichier aura une extension de fichier. cer ou. p7b, selon le codage que vous avez sélectionné à l’étape 3 de **pour télécharger le certificat d’autorité de certification**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-132">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>

11. <span data-ttu-id="f0c55-133">Cliquez sur **Placer tous les certificats dans le magasin suivant**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-133">Click **Place All Certificates in the following store**.</span></span>

12. <span data-ttu-id="f0c55-134">Cliquez sur **Parcourir**, puis sélectionnez **autorités de certification racines de confiance**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-134">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span>

13. <span data-ttu-id="f0c55-135">Cliquez sur **suivant** pour vérifier les paramètres, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-135">Click **Next** to verify the settings, and then click **Finish**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a><span data-ttu-id="f0c55-136">Pour vérifier que la CA figure dans la liste des autorités de certification racines de confiance</span><span class="sxs-lookup"><span data-stu-id="f0c55-136">To verify that the CA is in the list of trusted root CAs</span></span>

1.  <span data-ttu-id="f0c55-137">Sur le serveur exécutant la messagerie unifiée Exchange, dans MMC, développez **certificats (ordinateur local)**, développez **autorités de certification racine de confiance**, puis cliquez sur **certificats**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-137">On the server running Exchange UM, in MMC expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

2.  <span data-ttu-id="f0c55-138">Dans le volet Détails, vérifiez que votre AC figure dans la liste des autorités de certification approuvées.</span><span class="sxs-lookup"><span data-stu-id="f0c55-138">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a><span data-ttu-id="f0c55-139">Pour configurer la messagerie unifiée Exchange Server 2013 avec Lync Server</span><span class="sxs-lookup"><span data-stu-id="f0c55-139">To configure Exchange Server 2013 UM with Lync Server</span></span>

1.  <span data-ttu-id="f0c55-140">Pour plus d’informations, reportez-vous à la section « intégration de la messagerie unifiée Exchange 2013 à Lync Server » dans la documentation sur [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)le serveur Exchange.</span><span class="sxs-lookup"><span data-stu-id="f0c55-140">For details, see "Integrate Exchange 2013 UM with Lync Server" in the Exchange Server documentation at [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="f0c55-141">Pour créer une demande de certificat et installer le certificat sur Exchange Server 2007 (SP1)</span><span class="sxs-lookup"><span data-stu-id="f0c55-141">To create a certificate request and install the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="f0c55-142">Sur le serveur exécutant la messagerie unifiée Exchange, cliquez sur **Démarrer**, sur **exécuter**, tapez le nom **\<http://** de votre serveur**\>** de certification émettrice/certsrv, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-142">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<** name of your Issuing CA Server**\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="f0c55-143">Sous **Sélectionner une tâche**, cliquez sur **demander un certificat**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-143">Under **Select a task**, click **Request a Certificate**.</span></span>

3.  <span data-ttu-id="f0c55-144">Sous **demander un certificat**, cliquez sur **demande de certificat avancée**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-144">Under **Request a Certificate**, click **Advanced certificate request**.</span></span>

4.  <span data-ttu-id="f0c55-145">Sous **demande de certification avancée**, cliquez sur **créer et demander une demande à cette autorité de certification**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-145">Under **Advanced Certificate Request**, click **Create and submit a request to this CA**.</span></span>

5.  <span data-ttu-id="f0c55-146">Sous **demande de certification avancée**, sélectionnez **serveur Web** ou un autre modèle de certificat serveur configuré pour l’authentification du serveur.</span><span class="sxs-lookup"><span data-stu-id="f0c55-146">Under **Advanced Certificate Request**, select **Web server** or another server certificate template configured for server authentication.</span></span>

6.  <span data-ttu-id="f0c55-147">Sous **informations d’identification pour le modèle hors connexion**, dans la zone **nom** , tapez le nom de domaine complet (FQDN) du serveur Exchange.</span><span class="sxs-lookup"><span data-stu-id="f0c55-147">Under **Identifying Information for Offline Template**, in the **Name** box, type the fully qualified domain name (FQDN) of the Exchange Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f0c55-148">Vous devez entrer le nom de domaine complet (FQDN) du serveur Exchange sur lequel les communications fonctionneront.</span><span class="sxs-lookup"><span data-stu-id="f0c55-148">You must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

7.  <span data-ttu-id="f0c55-149">Sous **options**de la clé, cliquez sur la case à cocher **stocker le certificat dans le magasin de certificats de l’ordinateur local** .</span><span class="sxs-lookup"><span data-stu-id="f0c55-149">Under **Key Options**, click the **Store certificate in the local computer certificate store** check box.</span></span>

8.  <span data-ttu-id="f0c55-150">Cliquez sur le bouton de **soumission** en bas de la page Web.</span><span class="sxs-lookup"><span data-stu-id="f0c55-150">Click the **Submit** button in the bottom of the webpage.</span></span>

9.  <span data-ttu-id="f0c55-151">Dans la boîte de dialogue qui s’affiche, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-151">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

10. <span data-ttu-id="f0c55-152">Sur la page certificat émis, sous **certificat émis**, cliquez sur **installer ce certificat**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-152">On the Certificate Issued page, under **Certificate Issued**, click **Install this certificate**.</span></span>

11. <span data-ttu-id="f0c55-153">Dans la boîte de dialogue qui s’affiche, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-153">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

12. <span data-ttu-id="f0c55-154">Vérifiez que le message « votre nouveau certificat a été correctement installé » s’affiche.</span><span class="sxs-lookup"><span data-stu-id="f0c55-154">Verify that the message "Your new certificate has been successfully installed" appears.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a><span data-ttu-id="f0c55-155">Pour créer un certificat sur Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="f0c55-155">To create a certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="f0c55-156">Ouvrez une session sur le serveur exécutant la messagerie unifiée Exchange avec des droits d’utilisateur appropriés.</span><span class="sxs-lookup"><span data-stu-id="f0c55-156">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="f0c55-157">Pour plus d’informations, consultez la section « autorisations [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)d’accès client ».</span><span class="sxs-lookup"><span data-stu-id="f0c55-157">For details, see "Client Access Permissions" at [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="f0c55-158">Pour créer le certificat, consultez les procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="f0c55-158">Refer to the following procedures to create the certificate:</span></span>
    
    1.  <span data-ttu-id="f0c55-159">"Créer un nouveau certificat Exchange" à[http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)</span><span class="sxs-lookup"><span data-stu-id="f0c55-159">"Create a New Exchange Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)</span></span>
    
    2.  <span data-ttu-id="f0c55-160">« Importer un certificat Exchange » à[http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)</span><span class="sxs-lookup"><span data-stu-id="f0c55-160">"Import an Exchange Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f0c55-161">Pour le <STRONG>nom du sujet</STRONG>du certificat, vous devez entrer le nom de domaine complet (FQDN) du serveur Exchange sur lequel les communications doivent fonctionner.</span><span class="sxs-lookup"><span data-stu-id="f0c55-161">For the certificate <STRONG>Subject Name</STRONG>, you must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="f0c55-162">Pour attribuer le certificat sur Exchange Server 2007 (SP1)</span><span class="sxs-lookup"><span data-stu-id="f0c55-162">To assign the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="f0c55-163">Sur le serveur exécutant la messagerie unifiée Exchange, ouvrez la console MMC.</span><span class="sxs-lookup"><span data-stu-id="f0c55-163">On the server running Exchange UM, open MMC.</span></span>

2.  <span data-ttu-id="f0c55-164">Dans l’arborescence de la console, développez **personnel** , puis cliquez sur **certificats**.</span><span class="sxs-lookup"><span data-stu-id="f0c55-164">In the console tree, expand **Personal** and then click **Certificates**.</span></span>

3.  <span data-ttu-id="f0c55-165">Dans le volet Détails, assurez-vous que le certificat personnel est affiché.</span><span class="sxs-lookup"><span data-stu-id="f0c55-165">In the details pane, verify that personal certificate is displayed.</span></span>

4.  <span data-ttu-id="f0c55-166">Double-cliquez sur le certificat pour lire ses détails et vérifier qu’il est valide.</span><span class="sxs-lookup"><span data-stu-id="f0c55-166">Double-click the certificate to read its details and verify that it is valid.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f0c55-167">Le certificat est susceptible de prendre quelques minutes avant d’être affiché comme valide.</span><span class="sxs-lookup"><span data-stu-id="f0c55-167">It may take a few minutes before the certificate displays as valid.</span></span>

    
    </div>

5.  <span data-ttu-id="f0c55-168">Redémarrez le service de messagerie unifiée Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="f0c55-168">Restart the Microsoft Exchange Unified Messaging service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f0c55-169">Le serveur exécutant la messagerie unifiée Exchange Server 2007 SP1 récupère automatiquement le certificat approprié.</span><span class="sxs-lookup"><span data-stu-id="f0c55-169">The server running Exchange Server 2007 SP1 Unified Messaging automatically retrieves the correct certificate.</span></span>

    
    </div>

6.  <span data-ttu-id="f0c55-170">Ouvrez l’observateur d’événements et recherchez l’ID d’événement 1112, qui indique le certificat sur lequel le serveur exécutant la messagerie unifiée Exchange Server 2007 SP1 a récupéré.</span><span class="sxs-lookup"><span data-stu-id="f0c55-170">Open Event Viewer and look for Event ID 1112, which specifies what certificate the server running Exchange Server 2007 SP1 Unified Messaging has retrieved.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a><span data-ttu-id="f0c55-171">Pour attribuer le certificat sur Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="f0c55-171">To assign the certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="f0c55-172">Ouvrez une session sur le serveur exécutant la messagerie unifiée Exchange avec des droits d’utilisateur appropriés.</span><span class="sxs-lookup"><span data-stu-id="f0c55-172">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="f0c55-173">Pour plus d’informations, consultez la section « autorisations [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)d’accès client ».</span><span class="sxs-lookup"><span data-stu-id="f0c55-173">For details, see "Client Access Permissions" at [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="f0c55-174">Pour obtenir la procédure d’affectation d’un certificat, voir « attribuer des services à un [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497)certificat » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="f0c55-174">For the procedure to assign the certificate, see "Assign Services to a Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

