---
title: 'Lync Server 2013 : configuration des certificats pour l’interface Edge interne'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the internal edge interface
ms:assetid: a1963cc9-87c5-4935-86c0-6bedc6afd0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412750(v=OCS.15)
ms:contentKeyID: 48184949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1e43527c188b95863f2285c1adf4107ea53ebed
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a><span data-ttu-id="b3447-102">Configurer des certificats pour l’interface Edge interne dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3447-102">Set up certificates for the internal edge interface in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3447-103">_**Dernière modification de la rubrique :** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="b3447-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b3447-104">Lorsque vous exécutez l’Assistant Certificat, veillez à être connecté avec un compte membre d’un groupe auquel les autorisations appropriées ont été octroyées pour le type de modèle de certificat que vous allez utiliser.</span><span class="sxs-lookup"><span data-stu-id="b3447-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="b3447-105">Par défaut, une demande de certificat Lync Server 2013 utilisera le modèle de certificat de serveur Web.</span><span class="sxs-lookup"><span data-stu-id="b3447-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="b3447-106">Si vous utilisez un compte membre du groupe RTCUniversalServerAdmins pour demander un certificat qui utilise ce modèle, vérifiez que le groupe possède les autorisations d’inscription requises pour utiliser ce modèle.</span><span class="sxs-lookup"><span data-stu-id="b3447-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="b3447-107">Un certificat unique est requis sur l’interface interne de chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b3447-107">A single certificate is required on the internal interface of each Edge Server.</span></span> <span data-ttu-id="b3447-108">Les certificats pour l’interface interne peuvent être émis par une autorité de certification d’entreprise interne ou une autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="b3447-108">Certificates for the internal interface can be issued by an internal enterprise certification authority (CA) or a public CA.</span></span> <span data-ttu-id="b3447-109">Si votre organisation a déployé une autorité de certification interne, vous pouvez épargner sur les frais d’utilisation des certificats publics à l’aide de l’autorité de certification interne pour émettre le certificat pour l’interface interne.</span><span class="sxs-lookup"><span data-stu-id="b3447-109">If your organization has an internal CA deployed you can save on the expense of using public certificates by using the internal CA to issue the certificate for the internal interface.</span></span> <span data-ttu-id="b3447-110">Vous pouvez utiliser une autorité de certification Windows Server 2008 ou Windows Server 2008 R2 interne pour créer ces certificats.</span><span class="sxs-lookup"><span data-stu-id="b3447-110">You can use an internal Windows Server 2008 CA or Windows Server 2008 R2 CA to create these certificates.</span></span>

<span data-ttu-id="b3447-111">Pour plus d’informations à ce sujet et sur d’autres exigences de certificat, voir [Certificate Requirements for External User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="b3447-111">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="b3447-112">Pour configurer des certificats sur l’interface Edge interne au niveau d’un site, utilisez les procédures de cette section pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b3447-112">To set up certificates on the internal edge interface at a site, use the procedures in this section to do the following:</span></span>

1.  <span data-ttu-id="b3447-113">Téléchargez la chaîne de certification de l’autorité de certification pour l’interface interne sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b3447-113">Download the CA certification chain for the internal interface to each Edge Server.</span></span>

2.  <span data-ttu-id="b3447-114">Importez la chaîne de certification de l’autorité de certification pour l’interface interne sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b3447-114">Import the CA certification chain for the internal interface, on each Edge Server.</span></span>

3.  <span data-ttu-id="b3447-115">Créez la demande de certificat pour l’interface interne, sur un serveur Edge, appelé le premier serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b3447-115">Create the certificate request for the internal interface, on one Edge Server, called the first Edge Server.</span></span>

4.  <span data-ttu-id="b3447-116">Importez le certificat pour l’interface interne sur le premier serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b3447-116">Import the certificate for the internal interface on the first Edge Server.</span></span>

5.  <span data-ttu-id="b3447-117">Importez le certificat sur les autres serveurs Edge de ce site (ou déployé derrière cet équilibrage de charge).</span><span class="sxs-lookup"><span data-stu-id="b3447-117">Import the certificate on the other Edge Servers at this site (or deployed behind this load balancer).</span></span>

6.  <span data-ttu-id="b3447-118">Assignez le certificat pour l’interface interne de chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b3447-118">Assign the certificate for the internal interface of every Edge Server.</span></span>

<span data-ttu-id="b3447-119">Si vous avez plusieurs sites avec des serveurs Edge (c’est-à-dire, une topologie Edge sur plusieurs sites) ou des ensembles de serveurs Edge déployés derrière différents programmes d’équilibrage de la charge, vous devez suivre ces étapes pour chaque site doté de serveurs Edge et pour chaque ensemble de serveurs Edge. déployé derrière un programme d’équilibrage de charge différent.</span><span class="sxs-lookup"><span data-stu-id="b3447-119">If you have more than one site with Edge Servers (that is, a multiple-site edge topology), or separate sets of Edge Servers deployed behind different load balancers, you need to follow these steps for each site that has Edge Servers, and for each set of Edge Servers deployed behind a different load balancer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b3447-120">Les étapes des procédures décrites dans cette section sont basées sur l’utilisation d'&nbsp;une autorité de certification windows&nbsp;Server&nbsp;2008, Windows Server 2008 R2 ca, Windows server 2012 ca ou Windows Server 2012 R2 pour créer un certificat pour chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b3447-120">The steps for procedures in this section are based on using a Windows Server&nbsp;2008 CA, Windows Server&nbsp;2008&nbsp;R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA to create a certificate for each Edge Server.</span></span> <span data-ttu-id="b3447-121">Pour obtenir des instructions détaillées pour toute autre autorité de certification, consultez la documentation de cette autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="b3447-121">For step-by-step guidance for any other CA, consult the documentation for that CA.</span></span> <span data-ttu-id="b3447-122">Par défaut, tous les utilisateurs authentifiés disposent des droits d’utilisateur appropriés pour demander des certificats.</span><span class="sxs-lookup"><span data-stu-id="b3447-122">By default, all authenticated users have the appropriate user rights to request certificates.</span></span><BR><span data-ttu-id="b3447-123">Les procédures de cette section sont basées sur la création de demandes de certificats sur le serveur Edge dans le cadre du processus de déploiement du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b3447-123">The procedures in this section are based on creating certificate requests on the Edge Server as part of the Edge Server deployment process.</span></span> <span data-ttu-id="b3447-124">Il est possible de créer des demandes de certificat à l’aide du serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="b3447-124">It is possible to create certificate requests using the Front End Server.</span></span> <span data-ttu-id="b3447-125">Vous pouvez effectuer cette opération pour terminer la demande de certificat au début du processus de planification et de déploiement, avant de commencer le déploiement des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="b3447-125">You can do this to complete the certificate request early in the planning and deployment process, before you start deployment of the Edge Servers.</span></span> <span data-ttu-id="b3447-126">Pour ce faire, vous devez vous assurer que le certificat que vous demandez est défini avec une clé privée exportable.</span><span class="sxs-lookup"><span data-stu-id="b3447-126">To do this, you must ensure that the certificate you request is defined with an exportable private key.</span></span><BR><span data-ttu-id="b3447-127">Les procédures décrites dans cette section décrivent l’utilisation d’un fichier. cer et d’un fichier. p7b pour le certificat.</span><span class="sxs-lookup"><span data-stu-id="b3447-127">The procedures in this section describe using a .cer and a .p7b file for the certificate.</span></span> <span data-ttu-id="b3447-128">Si vous utilisez un autre type de fichier, modifiez ces procédures selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="b3447-128">If you use a different type of file, modify these procedures as appropriate.</span></span>



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a><span data-ttu-id="b3447-129">Pour télécharger la chaîne de certification de l’autorité de certification pour l’interface interne à l’aide du site Web certsrv</span><span class="sxs-lookup"><span data-stu-id="b3447-129">To download the CA certification chain for the internal interface using certsrv Web site</span></span>

1.  <span data-ttu-id="b3447-130">Connectez-vous à un serveur Lync Server 2013 sur le réseau interne (c’est-à-dire, pas au serveur Edge) en tant que membre du groupe **administrateurs** .</span><span class="sxs-lookup"><span data-stu-id="b3447-130">Log on to an Lync Server 2013 server in the internal network (that is, not the Edge Server) as a member of the **Administrators** group.</span></span>

2.  <span data-ttu-id="b3447-131">À l’invite de commandes, exécutez la commande suivante en cliquant sur **Démarrer**, sur **exécuter**, puis en tapant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="b3447-131">Run the following command at a command prompt by clicking **Start**, clicking **Run**, and then typing the following:</span></span>
    
        https://<name of your Issuing CA Server>/certsrv
    
    <span data-ttu-id="b3447-132">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b3447-132">For example:</span></span>
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b3447-133">Si vous utilisez une autorité de certification Windows Server 2008 ou Windows Server 2008 R2 Enterprise, vous devez utiliser le protocole HTTPS, et non http.</span><span class="sxs-lookup"><span data-stu-id="b3447-133">If you are using a Windows Server 2008 or Windows Server 2008 R2 enterprise CA, you must use https, not http.</span></span>

    
    </div>

3.  <span data-ttu-id="b3447-134">Sur la page Web certsrv de l’autorité de certification émettrice, sous **Sélectionner une tâche**, cliquez sur **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou une liste de révocation de**certificats.</span><span class="sxs-lookup"><span data-stu-id="b3447-134">On the issuing CA’s certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

4.  <span data-ttu-id="b3447-135">Sous **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou une liste de révocation de**certificats, cliquez sur **Télécharger la chaîne de certificat ca**.</span><span class="sxs-lookup"><span data-stu-id="b3447-135">Under **Download a CA Certificate, Certificate Chain, or CRL**, click **Download CA certificate chain**.</span></span>

5.  <span data-ttu-id="b3447-136">Dans la boîte de dialogue **Téléchargement de fichiers**, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b3447-136">In the **File Download** dialog box, click **Save**.</span></span>

6.  <span data-ttu-id="b3447-137">Enregistrez le fichier. p7b sur le disque dur du serveur, puis copiez-le dans un dossier sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b3447-137">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b3447-138">Le fichier. p7b contient tous les certificats qui se trouvent dans le chemin d’accès de certification.</span><span class="sxs-lookup"><span data-stu-id="b3447-138">The .p7b file contains all of the certificates that are in the certification path.</span></span> <span data-ttu-id="b3447-139">Pour afficher le chemin d’accès de certification, ouvrez le certificat de serveur et cliquez sur le chemin d’accès de certification.</span><span class="sxs-lookup"><span data-stu-id="b3447-139">To view the certification path, open the server certificate and click the certification path.</span></span>

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a><span data-ttu-id="b3447-140">Pour exporter la chaîne de certification de l’autorité de certification pour l’interface interne à l’aide de MMC</span><span class="sxs-lookup"><span data-stu-id="b3447-140">To export the CA certification chain for the internal interface using MMC</span></span>

1.  <span data-ttu-id="b3447-141">Vous pouvez exporter le certificat racine de l’autorité de certification à partir d’un ordinateur appartenant à un domaine à l’aide de la console MMC (Microsoft Management Console).</span><span class="sxs-lookup"><span data-stu-id="b3447-141">You can export the CA root certificate from any domain joined machine using the Microsoft Management Console (MMC).</span></span> <span data-ttu-id="b3447-142">Cliquez sur **Démarrer**, sur **exécuter**, puis tapez **MMC**.</span><span class="sxs-lookup"><span data-stu-id="b3447-142">Click **Start**, click **Run**, and then type **MMC**.</span></span>

2.  <span data-ttu-id="b3447-143">Dans la console MMC, cliquez sur **fichier**, puis sur **Ajouter/supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b3447-143">In the MMC console, click **File**, click **Add/Remove**.</span></span>

3.  <span data-ttu-id="b3447-144">Dans la liste de la boîte de dialogue **Ajouter ou supprimer des composants logiciels enfichables** , sélectionnez **certificats**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="b3447-144">From the **Add or Remove Snap-ins** dialog list, select **Certificates**, then click **Add**.</span></span> <span data-ttu-id="b3447-145">Lorsque vous y êtes invité, sélectionnez **compte d’ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="b3447-145">When prompted, select **Computer Account**.</span></span> <span data-ttu-id="b3447-146">Dans la boîte de dialogue **Sélectionner un ordinateur** , sélectionnez **ordinateur local**.</span><span class="sxs-lookup"><span data-stu-id="b3447-146">On the **Select Computer** dialog, select **Local Computer**.</span></span> <span data-ttu-id="b3447-147">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="b3447-147">Click **Finish**.</span></span> <span data-ttu-id="b3447-148">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3447-148">Click **OK**.</span></span>

4.  <span data-ttu-id="b3447-149">Développez **certificats (ordinateur local)**.</span><span class="sxs-lookup"><span data-stu-id="b3447-149">Expand **Certificates (Local Computer)**.</span></span> <span data-ttu-id="b3447-150">Développez **autorités de certification racines de confiance**, puis sélectionnez **certificats**.</span><span class="sxs-lookup"><span data-stu-id="b3447-150">Expand **Trusted Root Certification Authorities**, select **Certificates**.</span></span>

5.  <span data-ttu-id="b3447-151">Cliquez sur le certificat racine émis par votre autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="b3447-151">Click the root certificate issued by your CA.</span></span> <span data-ttu-id="b3447-152">Cliquez avec le bouton droit sur le certificat, sélectionnez **toutes les tâches**, sélectionnez **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="b3447-152">Right click the certificate, select **All Tasks**, select **Export**.</span></span> <span data-ttu-id="b3447-153">L' **Assistant exportation de certificat** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="b3447-153">The **Certificate Export Wizard** will open.</span></span>

6.  <span data-ttu-id="b3447-154">Dans l’**Assistant Exportation de certificat**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b3447-154">In the **Certificate Export Wizard**, click **Next**.</span></span>

7.  <span data-ttu-id="b3447-155">Dans la boîte de dialogue **Exporter le format de fichier** , sélectionnez un format d’exportation.</span><span class="sxs-lookup"><span data-stu-id="b3447-155">On the **Export File Format** dialog, select a format to export to.</span></span> <span data-ttu-id="b3447-156">Nous vous recommandons d’utiliser la **syntaxe de message \#de chiffrement standard – certificats PKCS 7 (. P7B)**.</span><span class="sxs-lookup"><span data-stu-id="b3447-156">We recommend the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**.</span></span> <span data-ttu-id="b3447-157">Si vous sélectionnez la **syntaxe de message chiffré standard – \#certificats PKCS 7 (. P7B)**, activez la case à cocher **inclure tous les certificats dans le chemin d’accès de certification si possible** pour exporter la chaîne de certificats, y compris le certificat de l’autorité de certification racine et les certificats de l’autorité de certification intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="b3447-157">If you select the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**, select the **Include all certificates in the certification path if possible** checkbox to export the certificate chain, including the root CA certificate and any Intermediate CA certificates.</span></span> <span data-ttu-id="b3447-158">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b3447-158">Click **Next**.</span></span>

8.  <span data-ttu-id="b3447-159">Dans la boîte de dialogue **fichier à exporter** de l’entrée nom de fichier, tapez un chemin d’accès et un nom de fichier (extension. p7b) pour le certificat exporté.</span><span class="sxs-lookup"><span data-stu-id="b3447-159">On the **File to Export** dialog in the file name entry, type a path and file name (default extension is .p7b) for the exported certificate.</span></span> <span data-ttu-id="b3447-160">Éventuellement, cliquez sur **Parcourir**, recherchez un répertoire dans lequel placer le certificat exporté et attribuez un nom au certificat exporté.</span><span class="sxs-lookup"><span data-stu-id="b3447-160">Optionally, click **Browse**, locate a directory to place the exported certificate in and provide a name for the exported certificate.</span></span> <span data-ttu-id="b3447-161">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b3447-161">Click **Save**.</span></span> <span data-ttu-id="b3447-162">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b3447-162">Click **Next**.</span></span>

9.  <span data-ttu-id="b3447-163">Examinez le résumé des actions, puis cliquez sur **Terminer** pour terminer l’exportation du certificat.</span><span class="sxs-lookup"><span data-stu-id="b3447-163">Review the summary of actions, and click **Finish** to complete the export of the certificate.</span></span> <span data-ttu-id="b3447-164">Cliquez sur **OK** pour confirmer l’exportation.</span><span class="sxs-lookup"><span data-stu-id="b3447-164">Click **OK** to confirm the successful export.</span></span>

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a><span data-ttu-id="b3447-165">Pour importer la chaîne de certification de l’autorité de certification pour l’interface interne</span><span class="sxs-lookup"><span data-stu-id="b3447-165">To import the CA certification chain for the internal interface</span></span>

1.  <span data-ttu-id="b3447-166">Sur chaque serveur Edge, ouvrez la console MMC (Microsoft Management Console) en cliquant sur **Démarrer**, puis sur **exécuter**, en tapant **MMC** dans la zone **ouvrir** , puis en cliquant sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3447-166">On each Edge Server, open the Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="b3447-167">Dans le menu **Fichier**, cliquez sur **Ajouter/Supprimer un composant logiciel enfichable**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="b3447-167">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="b3447-168">Dans la zone **Ajout d’un composant logiciel enfichable autonome**, cliquez sur **Certificats**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="b3447-168">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="b3447-169">Dans la boîte de dialogue **Composant logiciel enfichable Certificats**, cliquez sur **Compte d’ordinateur**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b3447-169">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="b3447-170">Dans la boîte de dialogue **Sélectionner un ordinateur**, assurez-vous que la case à cocher **Ordinateur local : (l’ordinateur sur lequel cette console s’exécute)** est activée, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="b3447-170">In the **Select Computer** dialog box, ensure that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="b3447-171">Cliquez sur **Fermer**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3447-171">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="b3447-172">Dans l’arborescence de la console, développez **certificats (ordinateur local)**, cliquez avec le bouton droit sur **autorités de certification racines de confiance**, pointez sur **toutes les tâches**, puis cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="b3447-172">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, point to **All Tasks**, and then click **Import**.</span></span>

8.  <span data-ttu-id="b3447-173">Dans l’Assistant, dans **fichier à importer**, spécifiez le nom de fichier du certificat (autrement dit, le nom de celui que vous avez spécifié lorsque vous avez téléchargé la chaîne de certification de l’autorité de certification pour l’interface interne dans la procédure précédente).</span><span class="sxs-lookup"><span data-stu-id="b3447-173">In the wizard, in **File to Import**, specify the file name of the certificate (that is, the name of that you specified when you downloaded the CA certification chain for the internal interface in the previous procedure).</span></span>

9.  <span data-ttu-id="b3447-174">Répétez cette procédure sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b3447-174">Repeat this procedure on each Edge Server.</span></span>

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a><span data-ttu-id="b3447-175">Pour créer la demande de certificat pour l’interface interne</span><span class="sxs-lookup"><span data-stu-id="b3447-175">To create the certificate request for the internal interface</span></span>

1.  <span data-ttu-id="b3447-176">Sur l’un des serveurs Edge, démarrez l’Assistant Déploiement et en regard de l' **étape 3 : demander, installer ou assigner les certificats**, cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="b3447-176">On one of the Edge Servers, start the Deployment Wizard, and next to **Step 3: Request, Install, or Assign Certificates**, click **Run**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b3447-177">Si vous disposez de plusieurs serveurs Edge dans un même emplacement d’un pool, vous pouvez exécuter l’Assistant certificat sur l’un des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="b3447-177">If you have multiple Edge Servers in one location in a pool, you can run the Certificate Wizard on any one of the Edge Servers.</span></span><BR><span data-ttu-id="b3447-178">Après avoir exécuté l’étape 3 pour la première fois, le bouton passe à <STRONG>réexécuter</STRONG>, et une coche verte indiquant que l’exécution de la tâche a réussi s’affiche jusqu’à ce que tous les certificats requis aient été demandés, installés et affectés.</span><span class="sxs-lookup"><span data-stu-id="b3447-178">After you run Step 3 the first time, the button changes to <STRONG>Run again</STRONG>, and a green check mark that indicates successful completion of the task is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

    
    </div>

2.  <span data-ttu-id="b3447-179">Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Créer une demande de certificat**.</span><span class="sxs-lookup"><span data-stu-id="b3447-179">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="b3447-180">Dans la page **Demande de certificat**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b3447-180">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="b3447-181">Sur la page **demandes différées ou immédiates** , cliquez sur **préparer la demande maintenant, mais l’envoyer plus tard**.</span><span class="sxs-lookup"><span data-stu-id="b3447-181">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>

5.  <span data-ttu-id="b3447-182">Dans la page **fichier de demande de certificat** , tapez le chemin d’accès complet et le nom du fichier dans lequel la demande doit être enregistrée (par exemple, **c :\\CERT\_Internal\_Edge. cer**).</span><span class="sxs-lookup"><span data-stu-id="b3447-182">On the **Certificate Request File** page, type the full path and file name to which the request is to be saved (for example, **c:\\cert\_internal\_edge.cer**).</span></span>

6.  <span data-ttu-id="b3447-183">Sur la page **spécifier un autre modèle de certificat** , pour utiliser un autre modèle que le modèle serveur Web par défaut, activez la case à cocher utiliser un autre modèle **de certificat pour l’autorité de certification sélectionnée** .</span><span class="sxs-lookup"><span data-stu-id="b3447-183">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>

7.  <span data-ttu-id="b3447-184">Dans la page **Nom et paramètres de sécurité**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b3447-184">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="b3447-185">Dans **nom convivial**, tapez un nom d’affichage pour le certificat (par exemple, Edge interne).</span><span class="sxs-lookup"><span data-stu-id="b3447-185">In **Friendly name**, type a display name for the certificate (for example, Internal Edge).</span></span>
    
      - <span data-ttu-id="b3447-186">Dans **longueur en bits**, spécifiez la longueur en bits (généralement, la valeur par défaut de **2048**).</span><span class="sxs-lookup"><span data-stu-id="b3447-186">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b3447-187">Les longueurs de bits plus élevées offrent davantage de sécurité, mais ont un impact négatif sur la vitesse.</span><span class="sxs-lookup"><span data-stu-id="b3447-187">Higher bit lengths offer more security, but they have a negative impact on speed.</span></span>

        
        </div>
    
      - <span data-ttu-id="b3447-188">Si le certificat doit être exportable, activez la case à cocher **marquer la clé privée du certificat comme exportable** .</span><span class="sxs-lookup"><span data-stu-id="b3447-188">If the certificate needs to be exportable, select the **Mark certificate private key as exportable** check box.</span></span>

8.  <span data-ttu-id="b3447-189">Sur la page informations sur l' **organisation** , tapez le nom de l’organisation et de l’unité d’organisation (ou) (par exemple, une division ou un service).</span><span class="sxs-lookup"><span data-stu-id="b3447-189">On the **Organization Information** page, type the name for the organization and the organizational unit (OU) (for example, a division or department).</span></span>

9.  <span data-ttu-id="b3447-190">Dans la page **Informations géographiques**, spécifiez les informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="b3447-190">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="b3447-191">Dans la page **Nom du sujet/Autres noms du sujet**, le système affiche les informations automatiquement renseignées par l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="b3447-191">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span>

11. <span data-ttu-id="b3447-192">Dans la page **Configurer d’autres noms du sujet supplémentaires** , spécifiez les autres noms du sujet supplémentaires nécessaires.</span><span class="sxs-lookup"><span data-stu-id="b3447-192">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

12. <span data-ttu-id="b3447-193">Sur la page Résumé de la **demande** , passez en revue les informations de certificat qui vont être utilisées pour générer la demande.</span><span class="sxs-lookup"><span data-stu-id="b3447-193">On the **Request Summary** page, review the certificate information that is going to be used to generate the request.</span></span>

13. <span data-ttu-id="b3447-194">Une fois les commandes terminées, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b3447-194">After the commands complete, do the following:</span></span>
    
      - <span data-ttu-id="b3447-195">Pour afficher le journal de la demande de certificat, cliquez sur **afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="b3447-195">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="b3447-196">Pour terminer la demande de certificat, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="b3447-196">To complete the certificate request, click **Next**.</span></span>

14. <span data-ttu-id="b3447-197">Dans la page **fichier de demande de certificat** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b3447-197">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="b3447-198">Pour afficher le fichier de demande de signature de certificat (CSR) généré, cliquez sur **Afficher**.</span><span class="sxs-lookup"><span data-stu-id="b3447-198">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="b3447-199">Pour fermer l’Assistant, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="b3447-199">To close the wizard, click **Finish**.</span></span>

15. <span data-ttu-id="b3447-200">Envoyez ce fichier à votre autorité de certification (par courrier électronique ou une autre méthode prise en charge par votre organisation pour votre autorité de certification d’entreprise) et, lorsque vous recevez le fichier de réponse, copiez le nouveau certificat sur cet ordinateur pour qu’il soit disponible pour l’importation.</span><span class="sxs-lookup"><span data-stu-id="b3447-200">Submit this file to your CA (by email or other method supported by your organization for your enterprise CA) and, when you receive the response file, copy the new certificate to this computer so that it is available for import.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a><span data-ttu-id="b3447-201">Pour importer le certificat pour l’interface interne</span><span class="sxs-lookup"><span data-stu-id="b3447-201">To import the certificate for the internal interface</span></span>

1.  <span data-ttu-id="b3447-202">Ouvrez une session sur le serveur Edge sur lequel vous avez créé la demande de certificat en tant que membre du groupe Administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="b3447-202">Log on to the Edge Server on which you created the certificate request as a member of the local Administrators group.</span></span>

2.  <span data-ttu-id="b3447-203">Dans l’Assistant Déploiement, en regard de **étape 3 : demander, installer ou assigner les certificats**, cliquez sur **réexécuter**.</span><span class="sxs-lookup"><span data-stu-id="b3447-203">In the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <span data-ttu-id="b3447-204">Après avoir exécuté l’étape 3 pour la première fois, le bouton passe à **réexécuter**, mais une coche verte (indiquant l’exécution réussie de la tâche) ne s’affiche qu’une fois que tous les certificats requis ont été demandés, installés et affectés.</span><span class="sxs-lookup"><span data-stu-id="b3447-204">After you run Step 3 the first time, the button changes to **Run again**, but a green check mark (indicating successful completion of the task) is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

3.  <span data-ttu-id="b3447-205">Sur la page **tâches de certificats disponibles** , cliquez sur **Importer un certificat à partir d’un. Fichier P7B,. pfx ou. cer**.</span><span class="sxs-lookup"><span data-stu-id="b3447-205">On the **Available Certificate Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>

4.  <span data-ttu-id="b3447-206">Sur la page **Importer un certificat** , tapez le chemin d’accès complet et le nom de fichier du certificat que vous avez demandé et reçu pour l’interface interne de ce serveur Edge (ou cliquez sur **Parcourir** pour rechercher et sélectionner le fichier).</span><span class="sxs-lookup"><span data-stu-id="b3447-206">On the **Import Certificate** page, type the full path and file name of the certificate that you requested and received for the internal interface of this Edge Server (or, click **Browse** to locate and select the file).</span></span>

5.  <span data-ttu-id="b3447-207">Si vous importez des certificats pour d’autres membres du pool, un certificat contenant une clé privée, activez la case à cocher le **fichier de certificat contient la clé privée du** certificat et spécifiez le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="b3447-207">If you are importing certificates for other members of the pool a certificate containing a private key, select the **Certificate file contains certifcate’s private key** check box and specify the password.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="b3447-208">Pour exporter le certificat avec la clé privée pour les serveurs Edge dans un pool</span><span class="sxs-lookup"><span data-stu-id="b3447-208">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="b3447-209">Ouvrez une session en tant que membre du groupe Administrateurs sur le serveur Edge sur lequel vous avez importé le certificat.</span><span class="sxs-lookup"><span data-stu-id="b3447-209">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="b3447-210">Cliquez sur **Démarrer**, sur **exécuter**, puis tapez **MMC**.</span><span class="sxs-lookup"><span data-stu-id="b3447-210">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="b3447-211">Dans la console MMC, cliquez sur **fichier**, puis sur **Ajouter/supprimer un composant logiciel enfichable**.</span><span class="sxs-lookup"><span data-stu-id="b3447-211">From the MMC console, click **File**, click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="b3447-212">Dans la page Ajouter ou supprimer des composants logiciels enfichables, cliquez sur **certificats**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="b3447-212">From Add or Remove Snap-ins page, click **Certificates**, click **Add**.</span></span>

5.  <span data-ttu-id="b3447-213">Dans la boîte de dialogue composant logiciel enfichable Certificats, sélectionnez **compte d’ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="b3447-213">In the Certificates snap-in dialog, select **Computer account**.</span></span> <span data-ttu-id="b3447-214">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b3447-214">Click **Next**.</span></span> <span data-ttu-id="b3447-215">Dans sélectionner un ordinateur, sélectionnez **ordinateur local : (l’ordinateur sur lequel cette console est exécutée)**.</span><span class="sxs-lookup"><span data-stu-id="b3447-215">In Select Computer, select **Local computer: (the computer this console is running on)**.</span></span> <span data-ttu-id="b3447-216">Cliquez sur**Terminer**.</span><span class="sxs-lookup"><span data-stu-id="b3447-216">Click **Finish**.</span></span> <span data-ttu-id="b3447-217">Cliquez sur **OK** pour terminer la configuration de la console MMC.</span><span class="sxs-lookup"><span data-stu-id="b3447-217">Click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="b3447-218">Double-cliquez sur **certificats (ordinateur local)** pour développer les magasins de certificats.</span><span class="sxs-lookup"><span data-stu-id="b3447-218">Double-click **Certificates (Local Computer)** to expand the certificate stores.</span></span> <span data-ttu-id="b3447-219">Double-cliquez sur **personnel**, puis sur **certificats**.</span><span class="sxs-lookup"><span data-stu-id="b3447-219">Double-click **Personal**, then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b3447-220">S’il n’y a aucun certificat dans le magasin personnel de certificats pour l’ordinateur local, il n’y a pas de clé privée associée au certificat importé.</span><span class="sxs-lookup"><span data-stu-id="b3447-220">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported.</span></span> <span data-ttu-id="b3447-221">Passez en revue les étapes de demande et d’importation.</span><span class="sxs-lookup"><span data-stu-id="b3447-221">Review the request and import steps.</span></span> <span data-ttu-id="b3447-222">Si le problème persiste, contactez l’administrateur de votre autorité de certification ou votre fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b3447-222">If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="b3447-223">Dans le magasin personnel de certificats de l’ordinateur local, cliquez avec le bouton droit sur le certificat que vous exportez.</span><span class="sxs-lookup"><span data-stu-id="b3447-223">In the Certificates Personal store for the local computer, right-click the certificate that you are exporting.</span></span> <span data-ttu-id="b3447-224">Cliquez sur **toutes les tâches**, puis sur **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="b3447-224">Click **All Tasks**, click **Export**.</span></span>

8.  <span data-ttu-id="b3447-225">Dans l’Assistant exportation de certificat, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="b3447-225">In the Certificate Export Wizard, click **Next**.</span></span> <span data-ttu-id="b3447-226">Sélectionnez **Oui, exporter la clé privée**.</span><span class="sxs-lookup"><span data-stu-id="b3447-226">Select **Yes, export the private key**.</span></span> <span data-ttu-id="b3447-227">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b3447-227">Click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b3447-228">Si la sélection est <STRONG>Oui, l’exportation de la clé privée</STRONG> n’est pas disponible, la clé privée associée à ce certificat n’a pas été marquée pour l’exportation.</span><span class="sxs-lookup"><span data-stu-id="b3447-228">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export.</span></span> <span data-ttu-id="b3447-229">Vous devrez demander de nouveau le certificat, en vous assurant que le certificat est marqué pour autoriser l’exportation de la clé privée avant de pouvoir poursuivre l’exportation.</span><span class="sxs-lookup"><span data-stu-id="b3447-229">You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export.</span></span> <span data-ttu-id="b3447-230">Contactez l’administrateur ou le fournisseur de votre autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="b3447-230">Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="b3447-231">Dans la boîte de dialogue Exporter les formats de fichiers, sélectionnez **échange\#d’informations personnelles – PKCS 12 (. PFX)** , puis sélectionnez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="b3447-231">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="b3447-232">Inclure tous les certificats dans le chemin d’accès de certification si possible</span><span class="sxs-lookup"><span data-stu-id="b3447-232">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="b3447-233">Exporter toutes les propriétés étendues</span><span class="sxs-lookup"><span data-stu-id="b3447-233">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="b3447-234">Lorsque vous exportez le certificat à partir d’un serveur Edge, ne sélectionnez pas <STRONG>Supprimer la clé privée si l’exportation réussit</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b3447-234">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>.</span></span> <span data-ttu-id="b3447-235">Si vous sélectionnez cette option, vous devez importer le certificat et la clé privée sur ce serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b3447-235">Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>
    
    <span data-ttu-id="b3447-236">Cliquez sur **Suivant** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="b3447-236">Click **Next** to continue.</span></span>

10. <span data-ttu-id="b3447-237">Si vous souhaitez affecter un mot de passe pour protéger la clé privée, tapez un mot de passe pour la clé privée.</span><span class="sxs-lookup"><span data-stu-id="b3447-237">If you want to assign password to protect the private key, type a password for the private key.</span></span> <span data-ttu-id="b3447-238">Entrez à nouveau le mot de passe pour le confirmer.</span><span class="sxs-lookup"><span data-stu-id="b3447-238">Re-enter the password to confirm.</span></span> <span data-ttu-id="b3447-239">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b3447-239">Click **Next**.</span></span>

11. <span data-ttu-id="b3447-240">Tapez un chemin d’accès et un nom de fichier pour le certificat exporté, à l’aide d’une extension de fichier. pfx.</span><span class="sxs-lookup"><span data-stu-id="b3447-240">Type a path and file name for the exported certificate, using a file extension of .pfx.</span></span> <span data-ttu-id="b3447-241">Le chemin d’accès doit être accessible à tous les autres serveurs Edge du pool ou être disponible pour le transport via un support amovible (par exemple, un lecteur flash USB).</span><span class="sxs-lookup"><span data-stu-id="b3447-241">The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive.</span></span> <span data-ttu-id="b3447-242">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b3447-242">Click **Next**.</span></span>

12. <span data-ttu-id="b3447-243">Consultez le résumé dans la boîte de dialogue fin de l’Assistant Exportation du certificat.</span><span class="sxs-lookup"><span data-stu-id="b3447-243">Review the summary on the Completing the Certificate Export Wizard dialog.</span></span> <span data-ttu-id="b3447-244">Cliquez sur**Terminer**.</span><span class="sxs-lookup"><span data-stu-id="b3447-244">Click **Finish**.</span></span>

13. <span data-ttu-id="b3447-245">Cliquez sur **OK** dans la boîte de dialogue d’exportation réussie.</span><span class="sxs-lookup"><span data-stu-id="b3447-245">Click **OK** in the successful export dialog.</span></span>

14. <span data-ttu-id="b3447-246">Importez le fichier de certificat exporté vers les autres serveurs Edge en suivant les étapes décrites dans les procédures [set up Certificates for the external Edge interface for Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="b3447-246">Import the exported certificate file to the other Edge servers following the steps outlined in the [Set up certificates for the external edge interface for Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) procedures.</span></span>

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a><span data-ttu-id="b3447-247">Pour affecter le certificat interne sur les serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="b3447-247">To assign the internal certificate on the Edge Servers</span></span>

1.  <span data-ttu-id="b3447-248">Sur chaque serveur Edge, dans l’Assistant Déploiement, à côté de **étape 3 : demander, installer ou assigner les certificats**, cliquez sur **réexécuter**.</span><span class="sxs-lookup"><span data-stu-id="b3447-248">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="b3447-249">Dans la page **tâches de certificats disponibles** , cliquez sur **affecter un certificat existant**.</span><span class="sxs-lookup"><span data-stu-id="b3447-249">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="b3447-250">Sur la page **affectation de certificat** , sélectionnez serveur **Edge interne** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="b3447-250">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>

4.  <span data-ttu-id="b3447-251">Sur la page **magasin de certificats** , sélectionnez le certificat que vous avez importé pour le serveur Edge interne (à partir de la procédure précédente).</span><span class="sxs-lookup"><span data-stu-id="b3447-251">On the **Certificate Store** page, select the certificate that you imported for the internal edge (from the previous procedure).</span></span>

5.  <span data-ttu-id="b3447-252">Sur la page Résumé de l' **affectation du certificat** , vérifiez vos paramètres, puis cliquez sur **suivant** pour affecter les certificats.</span><span class="sxs-lookup"><span data-stu-id="b3447-252">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

6.  <span data-ttu-id="b3447-253">Dans la page de fin de l’Assistant, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="b3447-253">On the wizard completion page, click **Finish**.</span></span>

7.  <span data-ttu-id="b3447-254">Après avoir utilisé cette procédure pour affecter le certificat Edge interne, ouvrez le composant logiciel enfichable certificat sur chaque serveur, développez **certificats (ordinateur local)**, développez **personnel**, cliquez sur **certificats**, puis vérifiez dans le volet d’informations que le certificat de périmètre interne est affiché.</span><span class="sxs-lookup"><span data-stu-id="b3447-254">After using this procedure to assign the internal edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the internal edge certificate is listed.</span></span>

8.  <span data-ttu-id="b3447-255">Si votre déploiement comprend plusieurs serveurs Edge, répétez cette procédure pour chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b3447-255">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

