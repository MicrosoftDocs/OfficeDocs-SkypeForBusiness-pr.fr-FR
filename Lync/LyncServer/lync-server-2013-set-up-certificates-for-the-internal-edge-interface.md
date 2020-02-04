---
title: 'Lync Server 2013 : Configuration des certificats pour l’interface interne Edge'
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
ms.openlocfilehash: ea6e462bdc629308493799c857ecb6b2434dc268
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a><span data-ttu-id="bd00a-102">Configuration des certificats pour l’interface interne Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd00a-102">Set up certificates for the internal edge interface in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd00a-103">_**Dernière modification de la rubrique :** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="bd00a-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bd00a-104">Lorsque vous exécutez l’Assistant certificat, assurez-vous que vous êtes connecté à l’aide d’un compte associé à un compte qui dispose des autorisations appropriées pour le type de modèle de certificat que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="bd00a-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="bd00a-105">Par défaut, une demande de certificat 2013 Lync Server utilise le modèle de certificat de serveur Web.</span><span class="sxs-lookup"><span data-stu-id="bd00a-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="bd00a-106">Si vous utilisez un compte membre du groupe RTCUniversalServerAdmins pour demander un certificat à l’aide de ce modèle, vérifiez que le groupe a été affecté aux autorisations d’inscription requises pour utiliser ce modèle.</span><span class="sxs-lookup"><span data-stu-id="bd00a-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="bd00a-107">Un certificat unique est requis sur l’interface interne de chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="bd00a-107">A single certificate is required on the internal interface of each Edge Server.</span></span> <span data-ttu-id="bd00a-108">Des certificats pour l’interface interne peuvent être émis par une autorité de certification d’entreprise interne ou une autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="bd00a-108">Certificates for the internal interface can be issued by an internal enterprise certification authority (CA) or a public CA.</span></span> <span data-ttu-id="bd00a-109">Si votre organisation a déployé une autorité de certification interne, vous pouvez faire des économies sur les frais d’utilisation des certificats publics à l’aide de l’autorité de certification interne pour émettre le certificat de l’interface interne.</span><span class="sxs-lookup"><span data-stu-id="bd00a-109">If your organization has an internal CA deployed you can save on the expense of using public certificates by using the internal CA to issue the certificate for the internal interface.</span></span> <span data-ttu-id="bd00a-110">Vous pouvez utiliser une autorité de certification Windows Server 2008 interne ou une autorité de certification Windows Server 2008 R2 pour créer ces certificats.</span><span class="sxs-lookup"><span data-stu-id="bd00a-110">You can use an internal Windows Server 2008 CA or Windows Server 2008 R2 CA to create these certificates.</span></span>

<span data-ttu-id="bd00a-111">Pour plus d’informations sur ce problème et sur les autres exigences relatives aux certificats, voir [exigences relatives aux certificats pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="bd00a-111">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="bd00a-112">Pour configurer des certificats sur l’interface latérale interne d’un site, suivez les procédures décrites dans cette section pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="bd00a-112">To set up certificates on the internal edge interface at a site, use the procedures in this section to do the following:</span></span>

1.  <span data-ttu-id="bd00a-113">Téléchargez la chaîne de certification de l’autorité de certification pour l’interface interne vers chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="bd00a-113">Download the CA certification chain for the internal interface to each Edge Server.</span></span>

2.  <span data-ttu-id="bd00a-114">Importez la chaîne de certification de l’autorité de certification pour l’interface interne sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="bd00a-114">Import the CA certification chain for the internal interface, on each Edge Server.</span></span>

3.  <span data-ttu-id="bd00a-115">Créez une demande de certificat pour l’interface interne, sur un serveur Edge, appelé le premier serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="bd00a-115">Create the certificate request for the internal interface, on one Edge Server, called the first Edge Server.</span></span>

4.  <span data-ttu-id="bd00a-116">Importez le certificat de l’interface interne sur le premier serveur de périphérie.</span><span class="sxs-lookup"><span data-stu-id="bd00a-116">Import the certificate for the internal interface on the first Edge Server.</span></span>

5.  <span data-ttu-id="bd00a-117">Importez le certificat sur les autres serveurs Edge sur ce site (ou déployé sur ce dernier).</span><span class="sxs-lookup"><span data-stu-id="bd00a-117">Import the certificate on the other Edge Servers at this site (or deployed behind this load balancer).</span></span>

6.  <span data-ttu-id="bd00a-118">Attribuez le certificat pour l’interface interne de chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="bd00a-118">Assign the certificate for the internal interface of every Edge Server.</span></span>

<span data-ttu-id="bd00a-119">Si vous disposez de plusieurs sites avec des serveurs de frontière (autrement dit, une topologie de périmètre de plusieurs sites), ou des ensembles séparés de serveurs de frontière déployés dans des équilibreurs de charge différents, vous devez suivre ces étapes pour chaque site incluant des serveurs de périphérie et pour chaque ensemble de serveurs de périphérie. déploiement à l’arrière-plan d’un autre équilibreur de charge.</span><span class="sxs-lookup"><span data-stu-id="bd00a-119">If you have more than one site with Edge Servers (that is, a multiple-site edge topology), or separate sets of Edge Servers deployed behind different load balancers, you need to follow these steps for each site that has Edge Servers, and for each set of Edge Servers deployed behind a different load balancer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bd00a-120">Les étapes décrites dans cette section sont basées sur l’utilisation d’une autorité&nbsp;de certification windows Server 2008&nbsp;,&nbsp;d’une autorité de certification Windows Server 2008 R2, d’une autorité de certification Windows Server 2012 ou d’une autorité de certification Windows Server 2012 R2 pour créer un certificat pour chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="bd00a-120">The steps for procedures in this section are based on using a Windows Server&nbsp;2008 CA, Windows Server&nbsp;2008&nbsp;R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA to create a certificate for each Edge Server.</span></span> <span data-ttu-id="bd00a-121">Pour obtenir des instructions détaillées pour une autre autorité de certification, consultez la documentation de cette autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="bd00a-121">For step-by-step guidance for any other CA, consult the documentation for that CA.</span></span> <span data-ttu-id="bd00a-122">Par défaut, tous les utilisateurs authentifiés disposent des droits d’utilisateur appropriés pour demander des certificats.</span><span class="sxs-lookup"><span data-stu-id="bd00a-122">By default, all authenticated users have the appropriate user rights to request certificates.</span></span><BR><span data-ttu-id="bd00a-123">Les procédures décrites dans cette section sont basées sur la création de demandes de certificat sur le serveur Edge dans le cadre du processus de déploiement de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="bd00a-123">The procedures in this section are based on creating certificate requests on the Edge Server as part of the Edge Server deployment process.</span></span> <span data-ttu-id="bd00a-124">Il est possible de créer des demandes de certificat à l’aide du serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="bd00a-124">It is possible to create certificate requests using the Front End Server.</span></span> <span data-ttu-id="bd00a-125">Vous pouvez le faire pour compléter la demande de certificat au début du processus de planification et de déploiement avant de commencer le déploiement des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="bd00a-125">You can do this to complete the certificate request early in the planning and deployment process, before you start deployment of the Edge Servers.</span></span> <span data-ttu-id="bd00a-126">Pour cela, vous devez vous assurer que le certificat que vous demandez est défini à l’aide d’une clé privée exportable.</span><span class="sxs-lookup"><span data-stu-id="bd00a-126">To do this, you must ensure that the certificate you request is defined with an exportable private key.</span></span><BR><span data-ttu-id="bd00a-127">Les procédures dans cette section décrivent l’utilisation d’un fichier. cer et d’un fichier. p7b pour le certificat.</span><span class="sxs-lookup"><span data-stu-id="bd00a-127">The procedures in this section describe using a .cer and a .p7b file for the certificate.</span></span> <span data-ttu-id="bd00a-128">Si vous utilisez un autre type de fichier, modifiez ces procédures selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="bd00a-128">If you use a different type of file, modify these procedures as appropriate.</span></span>



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a><span data-ttu-id="bd00a-129">Pour télécharger la chaîne de certification de l’autorité de certification pour l’interface interne à l’aide du site Web certsrv</span><span class="sxs-lookup"><span data-stu-id="bd00a-129">To download the CA certification chain for the internal interface using certsrv Web site</span></span>

1.  <span data-ttu-id="bd00a-130">Connectez-vous à un serveur Lync Server 2013 dans le réseau interne (c’est-à-dire hors du serveur Edge) en tant que membre du groupe **administrateurs** .</span><span class="sxs-lookup"><span data-stu-id="bd00a-130">Log on to an Lync Server 2013 server in the internal network (that is, not the Edge Server) as a member of the **Administrators** group.</span></span>

2.  <span data-ttu-id="bd00a-131">Exécutez la commande suivante à l’invite de commandes en cliquant sur **Démarrer**, puis en cliquant sur **exécuter**et en tapant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="bd00a-131">Run the following command at a command prompt by clicking **Start**, clicking **Run**, and then typing the following:</span></span>
    
        https://<name of your Issuing CA Server>/certsrv
    
    <span data-ttu-id="bd00a-132">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="bd00a-132">For example:</span></span>
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd00a-133">Si vous utilisez une autorité de certification Windows Server 2008 ou Windows Server 2008 R2 entreprise, vous devez utiliser HTTPS, et non http.</span><span class="sxs-lookup"><span data-stu-id="bd00a-133">If you are using a Windows Server 2008 or Windows Server 2008 R2 enterprise CA, you must use https, not http.</span></span>

    
    </div>

3.  <span data-ttu-id="bd00a-134">Dans la page web certsrv de l’autorité de certification émettrice, sous **Sélectionnez une tâche**, cliquez sur **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou la liste de révocation de certificats**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-134">On the issuing CA’s certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

4.  <span data-ttu-id="bd00a-135">Sous **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou une LRC**, cliquez sur **Télécharger la chaîne de certificats d’autorité**de certification.</span><span class="sxs-lookup"><span data-stu-id="bd00a-135">Under **Download a CA Certificate, Certificate Chain, or CRL**, click **Download CA certificate chain**.</span></span>

5.  <span data-ttu-id="bd00a-136">Dans la boîte de dialogue **téléchargement de fichier** , cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-136">In the **File Download** dialog box, click **Save**.</span></span>

6.  <span data-ttu-id="bd00a-137">Enregistrez le fichier. p7b sur le disque dur du serveur, puis copiez-le dans un dossier sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="bd00a-137">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd00a-138">Le fichier. p7b contient tous les certificats figurant dans le chemin de certification.</span><span class="sxs-lookup"><span data-stu-id="bd00a-138">The .p7b file contains all of the certificates that are in the certification path.</span></span> <span data-ttu-id="bd00a-139">Pour afficher le chemin d’accès de certification, ouvrez le certificat de serveur, puis cliquez sur le chemin d’accès de certification.</span><span class="sxs-lookup"><span data-stu-id="bd00a-139">To view the certification path, open the server certificate and click the certification path.</span></span>

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a><span data-ttu-id="bd00a-140">Pour exporter la chaîne de certification de l’autorité de certification pour l’interface interne à l’aide de MMC</span><span class="sxs-lookup"><span data-stu-id="bd00a-140">To export the CA certification chain for the internal interface using MMC</span></span>

1.  <span data-ttu-id="bd00a-141">Vous pouvez exporter le certificat racine de l’autorité de certification à partir de n’importe quel ordinateur sur lequel est connecté le domaine à l’aide de Microsoft Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="bd00a-141">You can export the CA root certificate from any domain joined machine using the Microsoft Management Console (MMC).</span></span> <span data-ttu-id="bd00a-142">Cliquez sur **Démarrer**, sur **exécuter**, puis tapez **MMC**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-142">Click **Start**, click **Run**, and then type **MMC**.</span></span>

2.  <span data-ttu-id="bd00a-143">Dans la console MMC, cliquez sur **fichier**, puis sur **Ajouter/supprimer**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-143">In the MMC console, click **File**, click **Add/Remove**.</span></span>

3.  <span data-ttu-id="bd00a-144">Dans la liste de la boîte de dialogue **Ajouter ou supprimer des composants additionnels** , sélectionnez **certificats**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-144">From the **Add or Remove Snap-ins** dialog list, select **Certificates**, then click **Add**.</span></span> <span data-ttu-id="bd00a-145">Lorsque vous y êtes invité, sélectionnez **compte d’ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-145">When prompted, select **Computer Account**.</span></span> <span data-ttu-id="bd00a-146">Dans la boîte de dialogue **Sélectionner un ordinateur**, sélectionnez **Ordinateur local**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-146">On the **Select Computer** dialog, select **Local Computer**.</span></span> <span data-ttu-id="bd00a-147">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-147">Click **Finish**.</span></span> <span data-ttu-id="bd00a-148">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-148">Click **OK**.</span></span>

4.  <span data-ttu-id="bd00a-149">Développez **certificats (ordinateur local)**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-149">Expand **Certificates (Local Computer)**.</span></span> <span data-ttu-id="bd00a-150">Développez **autorités de certification racine de confiance**, puis sélectionnez **certificats**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-150">Expand **Trusted Root Certification Authorities**, select **Certificates**.</span></span>

5.  <span data-ttu-id="bd00a-151">Cliquez sur le certificat racine émis par votre autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="bd00a-151">Click the root certificate issued by your CA.</span></span> <span data-ttu-id="bd00a-152">Cliquez avec le bouton droit sur le certificat, sélectionnez **toutes les tâches**, sélectionnez **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-152">Right click the certificate, select **All Tasks**, select **Export**.</span></span> <span data-ttu-id="bd00a-153">L' **Assistant exportation de certificat** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="bd00a-153">The **Certificate Export Wizard** will open.</span></span>

6.  <span data-ttu-id="bd00a-154">Dans l’**Assistant Exportation du certificat**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-154">In the **Certificate Export Wizard**, click **Next**.</span></span>

7.  <span data-ttu-id="bd00a-155">Dans la boîte de dialogue **Exporter le format de fichier** , sélectionnez le format d’exportation.</span><span class="sxs-lookup"><span data-stu-id="bd00a-155">On the **Export File Format** dialog, select a format to export to.</span></span> <span data-ttu-id="bd00a-156">Nous vous recommandons d’utiliser la **syntaxe de message \#cryptographique standard-certificats PKCS 7 (. P7B)**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-156">We recommend the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**.</span></span> <span data-ttu-id="bd00a-157">Si vous sélectionnez la **syntaxe de message cryptographique standard- \#certificats PKCS 7 (. P7B)**, activez la case à cocher **inclure tous les certificats dans le chemin de certification si possible** pour exporter la chaîne de certificats, y compris le certificat de l’autorité de certification racine et les certificats d’autorité de certification intermédiaires.</span><span class="sxs-lookup"><span data-stu-id="bd00a-157">If you select the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**, select the **Include all certificates in the certification path if possible** checkbox to export the certificate chain, including the root CA certificate and any Intermediate CA certificates.</span></span> <span data-ttu-id="bd00a-158">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-158">Click **Next**.</span></span>

8.  <span data-ttu-id="bd00a-159">Dans la boîte de dialogue **fichier à exporter** du nom de fichier, tapez le chemin d’accès et le nom du fichier (l’extension par défaut est. p7b) du certificat exporté.</span><span class="sxs-lookup"><span data-stu-id="bd00a-159">On the **File to Export** dialog in the file name entry, type a path and file name (default extension is .p7b) for the exported certificate.</span></span> <span data-ttu-id="bd00a-160">Vous pouvez également cliquer sur **Parcourir**, recherchez le répertoire dans lequel placer le certificat exporté et attribuez un nom au certificat exporté.</span><span class="sxs-lookup"><span data-stu-id="bd00a-160">Optionally, click **Browse**, locate a directory to place the exported certificate in and provide a name for the exported certificate.</span></span> <span data-ttu-id="bd00a-161">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-161">Click **Save**.</span></span> <span data-ttu-id="bd00a-162">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-162">Click **Next**.</span></span>

9.  <span data-ttu-id="bd00a-163">Examinez le résumé des actions, puis cliquez sur **Terminer** pour terminer l’exportation du certificat.</span><span class="sxs-lookup"><span data-stu-id="bd00a-163">Review the summary of actions, and click **Finish** to complete the export of the certificate.</span></span> <span data-ttu-id="bd00a-164">Cliquez sur **OK** pour confirmer l’exportation.</span><span class="sxs-lookup"><span data-stu-id="bd00a-164">Click **OK** to confirm the successful export.</span></span>

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a><span data-ttu-id="bd00a-165">Pour importer la chaîne de certification de l’autorité de certification pour l’interface interne</span><span class="sxs-lookup"><span data-stu-id="bd00a-165">To import the CA certification chain for the internal interface</span></span>

1.  <span data-ttu-id="bd00a-166">Sur chaque serveur Edge, ouvrez Microsoft Management Console (MMC) en cliquant sur **Démarrer**, sur **exécuter**, en tapant **MMC** dans la zone **ouvrir** , puis en cliquant sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-166">On each Edge Server, open the Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="bd00a-167">Dans le menu **fichier** , cliquez sur **Ajouter/supprimer un composant logiciel enfichable**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-167">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="bd00a-168">Dans la boîte de dialogue **Ajouter des composants logiciels enfichables autonomes** , cliquez sur **certificats**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-168">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="bd00a-169">Dans la boîte de dialogue **Composant logiciel enfichable Certificats**, cliquez sur **Compte d’ordinateur**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-169">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="bd00a-170">Dans la boîte de dialogue **Sélectionner un ordinateur** , assurez-vous que l' **ordinateur local (sur lequel cette console s’exécute)** est sélectionné, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-170">In the **Select Computer** dialog box, ensure that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="bd00a-171">Cliquez sur **Fermer**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-171">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="bd00a-172">Dans l’arborescence de la console, développez **certificats (ordinateur local)**, cliquez avec le bouton droit sur **autorités de certification racine de confiance**, pointez sur **toutes les tâches**, puis cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-172">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, point to **All Tasks**, and then click **Import**.</span></span>

8.  <span data-ttu-id="bd00a-173">Dans l’Assistant, dans **fichier à importer**, spécifiez le nom de fichier du certificat (autrement dit, le nom de l’interface que vous avez spécifiée lors du téléchargement de la chaîne de certification de l’autorité de certification pour l’interface interne au cours de la procédure précédente).</span><span class="sxs-lookup"><span data-stu-id="bd00a-173">In the wizard, in **File to Import**, specify the file name of the certificate (that is, the name of that you specified when you downloaded the CA certification chain for the internal interface in the previous procedure).</span></span>

9.  <span data-ttu-id="bd00a-174">Répétez cette procédure sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="bd00a-174">Repeat this procedure on each Edge Server.</span></span>

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a><span data-ttu-id="bd00a-175">Pour créer une demande de certificat pour l’interface interne</span><span class="sxs-lookup"><span data-stu-id="bd00a-175">To create the certificate request for the internal interface</span></span>

1.  <span data-ttu-id="bd00a-176">Sur l’un des serveurs Edge, démarrez l’Assistant Déploiement, puis, en regard de l' **étape 3 : demandez, installez ou attribuez des certificats**, cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-176">On one of the Edge Servers, start the Deployment Wizard, and next to **Step 3: Request, Install, or Assign Certificates**, click **Run**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd00a-177">Si vous avez plusieurs serveurs Edge à un emplacement dans un pool, vous pouvez exécuter l’Assistant certificat sur n’importe quel serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="bd00a-177">If you have multiple Edge Servers in one location in a pool, you can run the Certificate Wizard on any one of the Edge Servers.</span></span><BR><span data-ttu-id="bd00a-178">Après avoir exécuté l’étape 3 pour la première fois, le bouton est modifié pour <STRONG>s’exécuter de nouveau</STRONG>et une coche verte indiquant la réussite de la tâche n’est pas affichée tant que tous les certificats requis n’ont pas été demandés, installés et attribués.</span><span class="sxs-lookup"><span data-stu-id="bd00a-178">After you run Step 3 the first time, the button changes to <STRONG>Run again</STRONG>, and a green check mark that indicates successful completion of the task is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

    
    </div>

2.  <span data-ttu-id="bd00a-179">Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Créer une demande de certificat**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-179">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="bd00a-180">Dans la page **demande de certificat** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-180">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="bd00a-181">Dans la page **Demandes différées ou immédiates**, cliquez sur **Préparer la demande, mais ne pas l’envoyer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-181">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>

5.  <span data-ttu-id="bd00a-182">Dans la page **fichier de demande de certificat** , tapez le chemin d’accès complet et le nom du fichier vers lequel vous voulez enregistrer la requête (par exemple, **c :\\CERT\_Internal\_Edge. cer**).</span><span class="sxs-lookup"><span data-stu-id="bd00a-182">On the **Certificate Request File** page, type the full path and file name to which the request is to be saved (for example, **c:\\cert\_internal\_edge.cer**).</span></span>

6.  <span data-ttu-id="bd00a-183">Dans la page **spécifier un modèle de certificat secondaire** , pour utiliser un modèle autre que le modèle par défaut du serveur Web, activez la case à cocher utiliser un autre **modèle de certificat pour l’autorité de certification sélectionnée** .</span><span class="sxs-lookup"><span data-stu-id="bd00a-183">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>

7.  <span data-ttu-id="bd00a-184">Dans la page **paramètres de nom et de sécurité** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="bd00a-184">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="bd00a-185">Dans **nom convivial**, tapez un nom d’affichage pour le certificat (par exemple, bord interne).</span><span class="sxs-lookup"><span data-stu-id="bd00a-185">In **Friendly name**, type a display name for the certificate (for example, Internal Edge).</span></span>
    
      - <span data-ttu-id="bd00a-186">En **longueur**, spécifiez la longueur en bits (en général, la valeur par défaut **2048**).</span><span class="sxs-lookup"><span data-stu-id="bd00a-186">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bd00a-187">Des longueurs de bits plus élevées offrent une plus grande sécurité, mais ils ont un impact négatif sur la vitesse.</span><span class="sxs-lookup"><span data-stu-id="bd00a-187">Higher bit lengths offer more security, but they have a negative impact on speed.</span></span>

        
        </div>
    
      - <span data-ttu-id="bd00a-188">Si le certificat doit être exportable, activez la case à cocher **marquer le certificat comme étant exportable** .</span><span class="sxs-lookup"><span data-stu-id="bd00a-188">If the certificate needs to be exportable, select the **Mark certificate private key as exportable** check box.</span></span>

8.  <span data-ttu-id="bd00a-189">Dans la page informations sur l' **organisation** , tapez le nom de l’organisation et l’unité d’organisation (UO) (par exemple, une division ou un service).</span><span class="sxs-lookup"><span data-stu-id="bd00a-189">On the **Organization Information** page, type the name for the organization and the organizational unit (OU) (for example, a division or department).</span></span>

9.  <span data-ttu-id="bd00a-190">Dans la page **informations géographiques** , spécifiez les informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="bd00a-190">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="bd00a-191">Sur la page nom de l’objet **/nom** de l’objet, les informations à remplir automatiquement par l’Assistant sont affichées.</span><span class="sxs-lookup"><span data-stu-id="bd00a-191">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span>

11. <span data-ttu-id="bd00a-192">Dans la page **configurez** d’autres noms d’objet, spécifiez d’autres noms d’objet obligatoires.</span><span class="sxs-lookup"><span data-stu-id="bd00a-192">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

12. <span data-ttu-id="bd00a-193">Dans la page Résumé de la **demande** , passez en revue les informations de certificats qui vont être utilisées pour générer la requête.</span><span class="sxs-lookup"><span data-stu-id="bd00a-193">On the **Request Summary** page, review the certificate information that is going to be used to generate the request.</span></span>

13. <span data-ttu-id="bd00a-194">Une fois les commandes terminées, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="bd00a-194">After the commands complete, do the following:</span></span>
    
      - <span data-ttu-id="bd00a-195">Pour afficher le journal de la demande de certificat, cliquez sur **afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-195">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="bd00a-196">Pour remplir la demande de certificat, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-196">To complete the certificate request, click **Next**.</span></span>

14. <span data-ttu-id="bd00a-197">Dans la page **fichier de demande de certificat** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="bd00a-197">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="bd00a-198">Pour afficher le fichier de demande de signature de certificat généré (CSR), cliquez sur **Afficher**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-198">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="bd00a-199">Pour fermer l’Assistant, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-199">To close the wizard, click **Finish**.</span></span>

15. <span data-ttu-id="bd00a-200">Envoyez ce fichier à votre autorité de certification (par courrier électronique ou autre méthode prise en charge par votre organisation) et, lorsque vous recevez le fichier de réponse, copiez le nouveau certificat sur cet ordinateur pour qu’il soit disponible à des fins d’importation.</span><span class="sxs-lookup"><span data-stu-id="bd00a-200">Submit this file to your CA (by email or other method supported by your organization for your enterprise CA) and, when you receive the response file, copy the new certificate to this computer so that it is available for import.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a><span data-ttu-id="bd00a-201">Pour importer le certificat de l’interface interne</span><span class="sxs-lookup"><span data-stu-id="bd00a-201">To import the certificate for the internal interface</span></span>

1.  <span data-ttu-id="bd00a-202">Ouvrez une session sur le serveur Edge sur lequel vous avez créé la demande de certificat en tant que membre du groupe administrateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="bd00a-202">Log on to the Edge Server on which you created the certificate request as a member of the local Administrators group.</span></span>

2.  <span data-ttu-id="bd00a-203">Dans l’Assistant Déploiement, en regard de l' **étape 3 : demandez, installez ou attribuez des certificats**, cliquez de **nouveau sur exécuter**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-203">In the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <span data-ttu-id="bd00a-204">Après avoir exécuté l’étape 3 pour la première fois, le bouton est modifié pour **s’exécuter de nouveau**, mais une coche verte (indiquant la réussite de la tâche) ne s’affiche pas tant que tous les certificats requis n’ont pas été demandés, installés et attribués.</span><span class="sxs-lookup"><span data-stu-id="bd00a-204">After you run Step 3 the first time, the button changes to **Run again**, but a green check mark (indicating successful completion of the task) is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

3.  <span data-ttu-id="bd00a-205">Dans la page **tâches de certification disponibles** , cliquez sur **Importer un certificat à partir de a. Le fichier P7B,. pfx ou. cer**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-205">On the **Available Certificate Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>

4.  <span data-ttu-id="bd00a-206">Sur la page **importer le certificat** , tapez le chemin d’accès complet et le nom de fichier du certificat que vous avez demandé et reçu pour l’interface interne du serveur Edge (ou cliquez sur **Parcourir** pour rechercher et sélectionner le fichier).</span><span class="sxs-lookup"><span data-stu-id="bd00a-206">On the **Import Certificate** page, type the full path and file name of the certificate that you requested and received for the internal interface of this Edge Server (or, click **Browse** to locate and select the file).</span></span>

5.  <span data-ttu-id="bd00a-207">Si vous importez des certificats pour les autres membres du pool ayant un certificat contenant une clé privée, activez la case à cocher le **fichier de certificat contient la clé privée du** certificat et spécifiez le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="bd00a-207">If you are importing certificates for other members of the pool a certificate containing a private key, select the **Certificate file contains certifcate’s private key** check box and specify the password.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="bd00a-208">Pour exporter le certificat avec la clé privée pour les serveurs Edge dans un pool</span><span class="sxs-lookup"><span data-stu-id="bd00a-208">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="bd00a-209">Ouvrez une session en tant que membre du groupe Administrateurs sur le serveur Edge sur lequel vous avez importé le certificat.</span><span class="sxs-lookup"><span data-stu-id="bd00a-209">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="bd00a-210">Cliquez sur **Démarrer**, sur **exécuter**, puis tapez **MMC**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-210">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="bd00a-211">Dans la console MMC, cliquez sur **fichier**, puis sur **Ajouter/supprimer un composant logiciel enfichable**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-211">From the MMC console, click **File**, click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="bd00a-212">Dans la page Ajouter ou supprimer des composants logiciels enfichables, cliquez sur **certificats**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-212">From Add or Remove Snap-ins page, click **Certificates**, click **Add**.</span></span>

5.  <span data-ttu-id="bd00a-213">Dans la boîte de dialogue composant logiciel enfichable Certificats, sélectionnez **compte d’ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-213">In the Certificates snap-in dialog, select **Computer account**.</span></span> <span data-ttu-id="bd00a-214">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-214">Click **Next**.</span></span> <span data-ttu-id="bd00a-215">Sur votre ordinateur, sélectionnez **ordinateur local : (l’ordinateur sur lequel cette console s’exécute)**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-215">In Select Computer, select **Local computer: (the computer this console is running on)**.</span></span> <span data-ttu-id="bd00a-216">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-216">Click **Finish**.</span></span> <span data-ttu-id="bd00a-217">Cliquez sur **OK** pour terminer la configuration de la console MMC.</span><span class="sxs-lookup"><span data-stu-id="bd00a-217">Click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="bd00a-218">Double-cliquez sur **Certificats (ordinateur local)** pour développer les magasins de certificats.</span><span class="sxs-lookup"><span data-stu-id="bd00a-218">Double-click **Certificates (Local Computer)** to expand the certificate stores.</span></span> <span data-ttu-id="bd00a-219">Double-cliquez sur **personnel**, puis double-cliquez sur **certificats**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-219">Double-click **Personal**, then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bd00a-220">S’il n’y a aucun certificat dans le magasin personnel de certificats de l’ordinateur local, il n’existe aucune clé privée associée au certificat importé.</span><span class="sxs-lookup"><span data-stu-id="bd00a-220">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported.</span></span> <span data-ttu-id="bd00a-221">Passez en revue les étapes de demande et d’importation.</span><span class="sxs-lookup"><span data-stu-id="bd00a-221">Review the request and import steps.</span></span> <span data-ttu-id="bd00a-222">Si le problème persiste, contactez votre administrateur ou fournisseur de l’autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="bd00a-222">If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="bd00a-223">Dans le magasin personnel de certificats de l’ordinateur local, cliquez avec le bouton droit sur le certificat que vous exportez.</span><span class="sxs-lookup"><span data-stu-id="bd00a-223">In the Certificates Personal store for the local computer, right-click the certificate that you are exporting.</span></span> <span data-ttu-id="bd00a-224">Cliquez sur **toutes les tâches**, puis sur **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-224">Click **All Tasks**, click **Export**.</span></span>

8.  <span data-ttu-id="bd00a-225">Dans l’Assistant exportation de certificat, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-225">In the Certificate Export Wizard, click **Next**.</span></span> <span data-ttu-id="bd00a-226">Sélectionnez **Oui, exporter la clé privée**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-226">Select **Yes, export the private key**.</span></span> <span data-ttu-id="bd00a-227">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-227">Click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd00a-228">Si la sélection est <STRONG>Oui, exporter la clé privée</STRONG> n’est pas disponible, la clé privée associée à ce certificat n’est pas marquée pour l’exportation.</span><span class="sxs-lookup"><span data-stu-id="bd00a-228">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export.</span></span> <span data-ttu-id="bd00a-229">Vous devez demander à nouveau le certificat, en veillant à ce que le certificat soit marqué pour autoriser l’exportation de la clé privée avant de poursuivre l’exportation.</span><span class="sxs-lookup"><span data-stu-id="bd00a-229">You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export.</span></span> <span data-ttu-id="bd00a-230">Contactez votre administrateur ou fournisseur de l’autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="bd00a-230">Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="bd00a-231">Dans la boîte de dialogue Exporter les formats de fichier, sélectionnez **échange\#d’informations personnelles – PKCS 12 (. PFX)** , puis sélectionnez les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="bd00a-231">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="bd00a-232">Incluez tous les certificats dans le chemin de certification, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="bd00a-232">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="bd00a-233">Exporter toutes les propriétés étendues</span><span class="sxs-lookup"><span data-stu-id="bd00a-233">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="bd00a-234">Lorsque vous exportez le certificat à partir d’un serveur Edge, ne sélectionnez pas <STRONG>Supprimer la clé privée si l’exportation est réussie</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bd00a-234">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>.</span></span> <span data-ttu-id="bd00a-235">La sélection de cette option nécessite l’importation du certificat et de la clé privée vers ce serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="bd00a-235">Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>
    
    <span data-ttu-id="bd00a-236">Cliquez sur **Suivant** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="bd00a-236">Click **Next** to continue.</span></span>

10. <span data-ttu-id="bd00a-237">Si vous voulez affecter un mot de passe pour protéger la clé privée, tapez un mot de passe pour la clé privée.</span><span class="sxs-lookup"><span data-stu-id="bd00a-237">If you want to assign password to protect the private key, type a password for the private key.</span></span> <span data-ttu-id="bd00a-238">Entrez à nouveau le mot de passe pour le confirmer.</span><span class="sxs-lookup"><span data-stu-id="bd00a-238">Re-enter the password to confirm.</span></span> <span data-ttu-id="bd00a-239">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-239">Click **Next**.</span></span>

11. <span data-ttu-id="bd00a-240">Tapez un chemin d’accès et un nom de fichier avec l’extension .pfx pour le certificat exporté.</span><span class="sxs-lookup"><span data-stu-id="bd00a-240">Type a path and file name for the exported certificate, using a file extension of .pfx.</span></span> <span data-ttu-id="bd00a-241">Le chemin d’accès doit être accessible à tous les autres serveurs de périphérie du pool ou disponible pour le transport par le biais de médias amovibles (par exemple, un lecteur flash USB).</span><span class="sxs-lookup"><span data-stu-id="bd00a-241">The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive.</span></span> <span data-ttu-id="bd00a-242">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-242">Click **Next**.</span></span>

12. <span data-ttu-id="bd00a-243">Passez en revue le résumé de la boîte de dialogue de l’Assistant d’exportation de certificat.</span><span class="sxs-lookup"><span data-stu-id="bd00a-243">Review the summary on the Completing the Certificate Export Wizard dialog.</span></span> <span data-ttu-id="bd00a-244">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-244">Click **Finish**.</span></span>

13. <span data-ttu-id="bd00a-245">Cliquez sur **OK** dans la boîte de dialogue indiquant que l’exportation a abouti.</span><span class="sxs-lookup"><span data-stu-id="bd00a-245">Click **OK** in the successful export dialog.</span></span>

14. <span data-ttu-id="bd00a-246">Importez le fichier de certificat exporté vers les autres serveurs Edge en suivant les étapes décrites dans la rubrique [configurer des certificats pour les procédures Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="bd00a-246">Import the exported certificate file to the other Edge servers following the steps outlined in the [Set up certificates for the external edge interface for Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) procedures.</span></span>

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a><span data-ttu-id="bd00a-247">Pour affecter le certificat interne sur les serveurs de périphérie</span><span class="sxs-lookup"><span data-stu-id="bd00a-247">To assign the internal certificate on the Edge Servers</span></span>

1.  <span data-ttu-id="bd00a-248">Sur chaque serveur Edge, dans l’Assistant Déploiement, en regard de l' **étape 3 : demandez, installez ou attribuez des certificats**, cliquez de **nouveau sur exécuter**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-248">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="bd00a-249">Dans la page **tâches de certification disponibles** , cliquez sur **attribuer un certificat existant**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-249">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="bd00a-250">Dans la page **Affectation de certificat**, sélectionnez **Serveur Edge interne** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="bd00a-250">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>

4.  <span data-ttu-id="bd00a-251">Dans la page **magasin de certificats** , sélectionnez le certificat que vous avez importé pour le bord interne (à partir de la procédure précédente).</span><span class="sxs-lookup"><span data-stu-id="bd00a-251">On the **Certificate Store** page, select the certificate that you imported for the internal edge (from the previous procedure).</span></span>

5.  <span data-ttu-id="bd00a-252">Dans la page **Résumé des affectations de certificat** , passez en revue vos paramètres, puis cliquez sur **suivant** pour attribuer les certificats.</span><span class="sxs-lookup"><span data-stu-id="bd00a-252">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

6.  <span data-ttu-id="bd00a-253">Dans la page de fin de l’Assistant, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="bd00a-253">On the wizard completion page, click **Finish**.</span></span>

7.  <span data-ttu-id="bd00a-254">Lorsque vous utilisez cette procédure pour attribuer le certificat de bord interne, ouvrez le composant logiciel enfichable Certificats sur chaque serveur, développez **certificats (ordinateur local)**, développez **personnel**, cliquez sur **certificats**, puis vérifiez dans le volet d’informations que le certificat de bord interne est répertorié.</span><span class="sxs-lookup"><span data-stu-id="bd00a-254">After using this procedure to assign the internal edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the internal edge certificate is listed.</span></span>

8.  <span data-ttu-id="bd00a-255">Si votre déploiement inclut plusieurs serveurs Edge, répétez cette procédure pour chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="bd00a-255">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

