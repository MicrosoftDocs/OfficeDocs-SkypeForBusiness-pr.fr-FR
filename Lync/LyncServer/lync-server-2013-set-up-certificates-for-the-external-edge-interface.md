---
title: 'Lync Server 2013 : configuration des certificats pour l’interface Edge externe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the external edge interface
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398409(v=OCS.15)
ms:contentKeyID: 48184287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a190c50ece2b2e5be0f8597851541c71cfbb4e49
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509881"
---
# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a><span data-ttu-id="6ae69-102">Configurer des certificats pour l’interface Edge externe pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ae69-102">Set up certificates for the external edge interface for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ae69-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="6ae69-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6ae69-104">Lorsque vous exécutez l’Assistant Certificat, veillez à être connecté avec un compte membre d’un groupe auquel les autorisations appropriées ont été octroyées pour le type de modèle de certificat que vous allez utiliser.</span><span class="sxs-lookup"><span data-stu-id="6ae69-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="6ae69-105">Par défaut, une demande de certificat Lync Server utilise le modèle de certificat de serveur Web.</span><span class="sxs-lookup"><span data-stu-id="6ae69-105">By default, a Lync Server certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="6ae69-106">Si vous utilisez un compte membre du groupe RTCUniversalServerAdmins pour demander un certificat qui utilise ce modèle, vérifiez que le groupe possède les autorisations d’inscription requises pour utiliser ce modèle.</span><span class="sxs-lookup"><span data-stu-id="6ae69-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="6ae69-107">Chaque serveur Edge nécessite un certificat public sur l’interface entre le réseau de périmètre et Internet, et l’autre nom de sujet du certificat doit contenir les noms externes du service Edge d’accès et des noms de domaine complets (FQDN) du service Edge de conférence Web.</span><span class="sxs-lookup"><span data-stu-id="6ae69-107">Each Edge Server requires a public certificate on the interface between the perimeter network and the Internet, and the certificate’s subject alternative name must contain the external names of the Access Edge service and Web Conferencing Edge service fully qualified domain names (FQDNs).</span></span>

<span data-ttu-id="6ae69-108">Pour plus d’informations à ce sujet et sur d’autres exigences de certificat, voir [Certificate Requirements for External User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="6ae69-108">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="6ae69-109">Pour obtenir la liste des autorités de certification publiques qui fournissent des certificats conformes aux exigences spécifiques pour les certificats de communications unifiées et qui ont conclu un partenariat avec Microsoft afin de s’assurer qu’ils fonctionnent avec l’Assistant Certificat Lync Server 2013, consultez l’article 929395 de la base de connaissances Microsoft « partenaires de certificat de communications unifiées pour Exchange Server et Communications Server » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) .</span><span class="sxs-lookup"><span data-stu-id="6ae69-109">For a list of public certification authorities (CAs) that provide certificates that comply with specific requirements for unified communications certificates and have partnered with Microsoft to ensure they work with the Lync Server 2013 Certificate Wizard, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a><span data-ttu-id="6ae69-110">Configuration des certificats sur les interfaces externes</span><span class="sxs-lookup"><span data-stu-id="6ae69-110">Configuring Certificates on the External Interfaces</span></span>

<span data-ttu-id="6ae69-111">Pour configurer un certificat sur l’interface Edge externe sur un site, utilisez les procédures de cette section pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6ae69-111">To set up a certificate on the external edge interface at a site, use the procedures in this section to do the following:</span></span>

  - <span data-ttu-id="6ae69-112">Créez la demande de certificat pour l’interface externe du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="6ae69-112">Create the certificate request for the external interface of the Edge Server.</span></span>

  - <span data-ttu-id="6ae69-113">Envoyez la demande à votre autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="6ae69-113">Submit the request to your public CA.</span></span>

  - <span data-ttu-id="6ae69-114">Importez le certificat pour l’interface externe de chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="6ae69-114">Import the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="6ae69-115">Affectez le certificat pour l’interface externe de chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="6ae69-115">Assign the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="6ae69-116">Si votre déploiement comprend plusieurs serveurs Edge, exportez le certificat avec sa clé privée, puis copiez-le sur les autres serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="6ae69-116">If your deployment includes multiple Edge Servers, export the certificate along with its private key, and then copy it to the other Edge Servers.</span></span> <span data-ttu-id="6ae69-117">Ensuite, pour chaque serveur Edge, importez-le et affectez-le comme décrit précédemment.</span><span class="sxs-lookup"><span data-stu-id="6ae69-117">Then, for each Edge Server, import it and assign it as previously described.</span></span> <span data-ttu-id="6ae69-118">Répétez cette procédure pour chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="6ae69-118">Repeat this procedure for each Edge Server.</span></span>

<span data-ttu-id="6ae69-119">Vous pouvez demander des certificats publics directement auprès d’une autorité de certification publique (par exemple, à partir du site Web d’une autorité de certification publique).</span><span class="sxs-lookup"><span data-stu-id="6ae69-119">You can request public certificates directly from a public certification authority (CA) (such as from the website of a public CA).</span></span> <span data-ttu-id="6ae69-120">Les procédures de cette section utilisent l’Assistant Certificat pour la plupart des tâches de certificat.</span><span class="sxs-lookup"><span data-stu-id="6ae69-120">The procedures in this section use the Certificate Wizard for most certificate tasks.</span></span> <span data-ttu-id="6ae69-121">Si vous avez choisi de demander un certificat directement auprès d’une autorité de certification publique, vous devrez modifier chaque procédure comme il convient pour demander, transporter et importer le certificat, ainsi que pour importer la chaîne de certificats.</span><span class="sxs-lookup"><span data-stu-id="6ae69-121">If you chose to request a certificate directly from a public CA, then you will need to modify each procedure as appropriate to request, transport, and import the certificate and also to import the certificate chain.</span></span>

<span data-ttu-id="6ae69-122">Lorsque vous demandez un certificat à une autorité de certification externe, les informations d’identification fournies doivent disposer des autorisations nécessaires pour demander un certificat à cette autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="6ae69-122">When you request a certificate from an External CA, the credentials provided must have rights to request a certificate from that CA.</span></span> <span data-ttu-id="6ae69-123">Chaque autorité de certification dispose d’une stratégie de sécurité qui définit les informations d’identification (c’est-à-dire, les noms d’utilisateur et de groupe spécifiques) qui sont autorisées à demander, à émettre, à gérer ou à lire des certificats.</span><span class="sxs-lookup"><span data-stu-id="6ae69-123">Each CA has a security policy that defines which credentials (that is, specific user and group names) are allowed to request, issue, manage, or read certificates.</span></span>

<span data-ttu-id="6ae69-124">Si vous décidez d’utiliser la console MMC (Microsoft Management Console) certificats pour importer la chaîne de certificats et le certificat, vous devez les importer dans le magasin de certificats de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="6ae69-124">If you decide to use the Certificates Microsoft Management Console (MMC) to import the certificate chain and certificate, you must import them to the certificate store for the computer.</span></span> <span data-ttu-id="6ae69-125">Si vous les importez dans le magasin de certificats d’utilisateur ou de service, le certificat ne sera pas disponible pour affectation dans l’Assistant Certificat Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6ae69-125">If you import them to the user or service certificate store, the certificate will not be available for assignment in the Lync Server 2013 Certificate Wizard.</span></span>

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="6ae69-126">Pour créer la demande de certificat pour l’interface externe du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="6ae69-126">To create the certificate request for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="6ae69-127">Sur le serveur Edge, dans l’Assistant Déploiement, à côté d’**Étape 3 : Demander, installer ou assigner les certificats**, cliquez sur **Réexécuter**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-127">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ae69-128">Si votre organisation souhaite prendre en charge la connectivité PIC avec AOL, vous ne pouvez pas utiliser l’Assistant Déploiement de Lync Server pour demander le certificat.</span><span class="sxs-lookup"><span data-stu-id="6ae69-128">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="6ae69-129">Au lieu de cela, effectuez les étapes de la procédure « pour créer une demande de certificat pour l’interface externe du serveur Edge pour la prise en charge de la connectivité PIC avec AOL », plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="6ae69-129">Instead, perform the steps in the “To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL” procedure later in this topic.</span></span><BR><span data-ttu-id="6ae69-130">Si vous disposez de plusieurs serveurs Edge dans un même emplacement d’un pool, vous pouvez exécuter l’Assistant Certificat Lync Server 2013 sur l’un des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="6ae69-130">If you have multiple Edge Servers in one location in a pool, you can run the Lync Server 2013 Certificate Wizard on any one of the Edge Servers.</span></span>

    
    </div>

2.  <span data-ttu-id="6ae69-131">Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Créer une demande de certificat**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-131">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="6ae69-132">Dans la page **Demande de certificat**, cliquez sur **Certificat de serveur Edge externe**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-132">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="6ae69-133">Dans la page **Demande différée ou immédiate**, cochez la case **Préparer la demande maintenant, mais l’envoyer plus tard**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-133">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="6ae69-134">Dans la page **fichier de demande de certificat** , tapez le chemin d’accès complet et le nom du fichier dans lequel la demande doit être enregistrée (par exemple, c : \\ CERT \_ exernal \_ Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="6ae69-134">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="6ae69-135">Dans la page **Spécifier un autre modèle de certificat**, pour utiliser un autre modèle que le modèle WebServer par défaut, cochez la case **Utiliser un autre modèle de certificat pour l’autorité de certification sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-135">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="6ae69-136">Dans la page **Nom et paramètres de sécurité**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="6ae69-136">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="6ae69-137">Dans **Nom convivial**, tapez un nom d’affichage du certificat.</span><span class="sxs-lookup"><span data-stu-id="6ae69-137">In **Friendly name**, type a display name for the certificate.</span></span>
    
      - <span data-ttu-id="6ae69-138">Dans **longueur en bits**, spécifiez la longueur en bits (généralement, la valeur par défaut de **2048**).</span><span class="sxs-lookup"><span data-stu-id="6ae69-138">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
    
      - <span data-ttu-id="6ae69-139">Vérifiez que la case **Marquer la clé privée du certificat comme exportable** est cochée.</span><span class="sxs-lookup"><span data-stu-id="6ae69-139">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="6ae69-140">Dans la page **Informations relatives à l’organisation**, tapez le nom de l’organisation et de l’unité d’organisation (par exemple, une division ou un service).</span><span class="sxs-lookup"><span data-stu-id="6ae69-140">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="6ae69-141">Dans la page **Informations géographiques**, spécifiez les informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="6ae69-141">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="6ae69-p107">Dans la page **Nom du sujet/Autres noms du sujet**, le système affiche les informations automatiquement renseignées par l’Assistant. Si d’autres noms du sujet doivent être ajoutés, spécifiez-les dans les deux étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="6ae69-p107">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="6ae69-144">Sur la page **paramètre du domaine SIP sur les autres noms du sujet** , activez la case à cocher domaine pour ajouter un SIP.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="6ae69-144">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\></span></span> <span data-ttu-id="6ae69-145">entrée de la liste des autres noms du sujet.</span><span class="sxs-lookup"><span data-stu-id="6ae69-145">entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="6ae69-146">Dans la page **Configurer d’autres noms du sujet supplémentaires** , spécifiez les autres noms du sujet supplémentaires nécessaires.</span><span class="sxs-lookup"><span data-stu-id="6ae69-146">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

13. <span data-ttu-id="6ae69-147">Dans la page **Résumé de la demande**, vérifiez les informations de certificat à utiliser pour générer la demande.</span><span class="sxs-lookup"><span data-stu-id="6ae69-147">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="6ae69-148">Une fois l’exécution des commandes terminée, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="6ae69-148">After the commands finish running, do the following:</span></span>
    
      - <span data-ttu-id="6ae69-149">Pour afficher le journal de la demande de certificat, cliquez sur **afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-149">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="6ae69-150">Pour terminer la demande de certificat, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-150">To complete the certificate request, click **Next**.</span></span>

15. <span data-ttu-id="6ae69-151">Dans la page **fichier de demande de certificat** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="6ae69-151">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="6ae69-152">Pour afficher le fichier de demande de signature de certificat (CSR) généré, cliquez sur **Afficher**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-152">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="6ae69-153">Pour fermer l’Assistant, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-153">To close the wizard, click **Finish**.</span></span>

16. <span data-ttu-id="6ae69-154">Copiez le fichier de sortie dans un emplacement où vous pouvez l’envoyer à l’autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="6ae69-154">Copy the output file to a location where you can submit it to the public CA.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="6ae69-155">Pour créer une demande de certificat pour l’interface externe du serveur Edge, afin de prendre en charge la connectivité PIC avec AOL</span><span class="sxs-lookup"><span data-stu-id="6ae69-155">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="6ae69-156">Lorsque le modèle requis est disponible pour l’autorité de certification, utilisez la cmdlet Windows PowerShell suivante à partir du serveur Edge pour demander le certificat :</span><span class="sxs-lookup"><span data-stu-id="6ae69-156">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate:</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="6ae69-157">Le nom de certificat par défaut du modèle fourni dans Lync Server 2013 est le serveur Web.</span><span class="sxs-lookup"><span data-stu-id="6ae69-157">The default certificate name of the template provided in Lync Server 2013 is Web Server.</span></span> <span data-ttu-id="6ae69-158">Spécifiez uniquement le \<template name\> si vous devez utiliser un modèle qui est différent du modèle par défaut.</span><span class="sxs-lookup"><span data-stu-id="6ae69-158">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ae69-159">Si votre organisation souhaite prendre en charge la connectivité PIC avec AOL, vous devez utiliser Windows PowerShell au lieu de l’Assistant Certificat pour demander que le certificat soit attribué au serveur Edge externe pour le service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="6ae69-159">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="6ae69-160">Cela est dû au fait que le modèle de serveur Web Lync Server 2013 que l’Assistant certificat utilise pour demander un certificat ne prend pas en charge la configuration EKU du client.</span><span class="sxs-lookup"><span data-stu-id="6ae69-160">This is because the Lync Server 2013 Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="6ae69-161">Avant d’utiliser Windows PowerShell pour créer le certificat, l’administrateur de l’autorité de certification doit créer et déployer un nouveau modèle qui prend en charge l’utilisation améliorée de la variable client.</span><span class="sxs-lookup"><span data-stu-id="6ae69-161">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a><span data-ttu-id="6ae69-162">Pour envoyer une demande à une autorité de certification publique</span><span class="sxs-lookup"><span data-stu-id="6ae69-162">To submit a request to a public certification authority</span></span>

1.  <span data-ttu-id="6ae69-163">Ouvrez le fichier de sortie.</span><span class="sxs-lookup"><span data-stu-id="6ae69-163">Open the output file.</span></span>

2.  <span data-ttu-id="6ae69-164">Copiez et collez le contenu de la demande de signature de certificat (CSR).</span><span class="sxs-lookup"><span data-stu-id="6ae69-164">Copy and paste the contents of the Certificate Signing Request (CSR).</span></span>

3.  <span data-ttu-id="6ae69-165">Si vous y êtes invité, spécifiez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="6ae69-165">If prompted, specify the following:</span></span>
    
      - <span data-ttu-id="6ae69-166">**Microsoft** en tant que plateforme serveur.</span><span class="sxs-lookup"><span data-stu-id="6ae69-166">**Microsoft** as the server platform.</span></span>
    
      - <span data-ttu-id="6ae69-167">**IIS** comme version.</span><span class="sxs-lookup"><span data-stu-id="6ae69-167">**IIS** as the version.</span></span>
    
      - <span data-ttu-id="6ae69-168">**Serveur Web** en tant que type d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="6ae69-168">**Web Server** as the usage type.</span></span>
    
      - <span data-ttu-id="6ae69-169">**PKCS7** en tant que format de réponse.</span><span class="sxs-lookup"><span data-stu-id="6ae69-169">**PKCS7** as the response format.</span></span>

4.  <span data-ttu-id="6ae69-170">Lorsque l’autorité de certification publique a vérifié vos informations, vous recevez un message électronique contenant le texte requis pour votre certificat.</span><span class="sxs-lookup"><span data-stu-id="6ae69-170">When the public CA has verified your information, you will receive an email message containing text required for your certificate.</span></span>

5.  <span data-ttu-id="6ae69-171">Copiez le texte du message électronique et enregistrez-le dans un fichier texte (. txt) sur votre ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="6ae69-171">Copy the text from the email message and save the contents in a text file (.txt) on your local computer.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="6ae69-172">Pour importer le certificat pour l’interface externe du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="6ae69-172">To import the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="6ae69-173">Ouvrez une session en tant que membre du groupe Administrateurs sur le serveur Edge sur lequel vous avez créé la demande de certificat.</span><span class="sxs-lookup"><span data-stu-id="6ae69-173">Log on as a member of the Administrators group to the same Edge Server on which you created the certificate request.</span></span>

2.  <span data-ttu-id="6ae69-174">Dans l’Assistant Déploiement, dans la page **déployer le serveur Edge** , en regard de **étape 3 : demander, installer ou assigner les certificats**, cliquez sur **réexécuter**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-174">In the Deployment Wizard, on the **Deploy Edge Server** page, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

3.  <span data-ttu-id="6ae69-175">Sur la page **tâches de certificats disponibles** , cliquez sur **Importer un certificat à partir d’un fichier. p7b, pfx ou. cer**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-175">On the **Available Certificate Tasks** page, click **Import a certificate from a .p7b, pfx or .cer file**.</span></span>

4.  <span data-ttu-id="6ae69-176">Sur la page **Importer un certificat** , cliquez sur **Parcourir** pour rechercher et sélectionner le certificat que vous avez demandé pour l’interface externe du serveur Edge (ou, vous pouvez taper le chemin d’accès complet et le nom de fichier).</span><span class="sxs-lookup"><span data-stu-id="6ae69-176">On the **Import Certificate** page, click **Browse** to locate and select the certificate that you requested for the external interface of the Edge Server (or, you can type the full path and file name).</span></span> <span data-ttu-id="6ae69-177">Si le certificat contient une clé privée, sélectionnez le **fichier de certificat contient la clé privée du certificat** et tapez le mot de passe de la clé privée.</span><span class="sxs-lookup"><span data-stu-id="6ae69-177">If the certificate contains a private key, select **Certificate file contains certificate’s private key** and type the password for the private key.</span></span> <span data-ttu-id="6ae69-178">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-178">Click **Next**.</span></span>

5.  <span data-ttu-id="6ae69-179">Dans la page **importer le résumé du certificat** , passez en revue le résumé, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-179">On **Import Certificate Summary** page, review the summary and then click **Next**.</span></span>

6.  <span data-ttu-id="6ae69-180">Lors de l' **exécution de commandes**, passez en revue les résultats de l’importation, cliquez sur **afficher le journal** pour obtenir plus d’informations, puis cliquez sur **Terminer** pour terminer l’importation du certificat.</span><span class="sxs-lookup"><span data-stu-id="6ae69-180">On **Executing Commands**, review the results of the import, click **View Log** for more information as needed, and then click **Finish** to complete the certificate import.</span></span>

7.  <span data-ttu-id="6ae69-181">Si vous configurez un pool de serveurs Edge, exportez le certificat avec sa clé privée comme indiqué dans la procédure « pour exporter le certificat avec la clé privée pour les serveurs Edge dans un pool » plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="6ae69-181">If you are configuring an Edge Server pool, export the certificate with its private key as outlined in the “To export the certificate with the private key for Edge Servers in a pool” procedure later in this topic.</span></span> <span data-ttu-id="6ae69-182">Copiez le fichier de certificat exporté vers les autres serveurs Edge et importez-le dans le magasin de l’ordinateur sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="6ae69-182">Copy the exported certificate file to the other Edge Servers, and import it into the computer store on each Edge Server.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="6ae69-183">Pour exporter le certificat avec la clé privée pour les serveurs Edge dans un pool</span><span class="sxs-lookup"><span data-stu-id="6ae69-183">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="6ae69-184">Ouvrez une session en tant que membre du groupe Administrateurs sur le serveur Edge sur lequel vous avez importé le certificat.</span><span class="sxs-lookup"><span data-stu-id="6ae69-184">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="6ae69-185">Cliquez sur **Démarrer**, sur **exécuter**, puis tapez **MMC**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-185">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="6ae69-186">Dans la console MMC (Microsoft Management Console), cliquez sur **fichier**, puis sur **Ajouter/supprimer un composant logiciel enfichable**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-186">In the Microsoft Management Console (MMC) console, click **File**, and then click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="6ae69-187">Dans **Ajouter ou supprimer des composants logiciels enfichables**, cliquez sur **certificats**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-187">In **Add or Remove Snap-ins**, click **Certificates**, and then click **Add**.</span></span>

5.  <span data-ttu-id="6ae69-188">Dans la boîte de dialogue **certificats** , sélectionnez **compte d’ordinateur**, cliquez sur **suivant**, sélectionnez **ordinateur local : (l’ordinateur sur lequel cette console est exécutée)** dans **Sélectionner un ordinateur**, cliquez sur **Terminer** , puis sur **OK** pour terminer la configuration de la console MMC.</span><span class="sxs-lookup"><span data-stu-id="6ae69-188">In the **Certificates** dialog box, select **Computer account**, click **Next**, select **Local computer: (the computer this console is running on)** in **Select Computer**, click **Finish** and then click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="6ae69-189">Double-cliquez sur **certificats (ordinateur local)** pour développer les magasins de certificats, double-cliquez sur **personnel**, puis sur **certificats**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-189">Double-click **Certificates (Local Computer)** to expand the certificate stores, double-click **Personal**, and then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6ae69-190">S’il n’y a aucun certificat dans le magasin personnel de certificats pour l’ordinateur local, il n’y a pas de clé privée associée au certificat importé.</span><span class="sxs-lookup"><span data-stu-id="6ae69-190">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported.</span></span> <span data-ttu-id="6ae69-191">Passez en revue les étapes de demande et d’importation.</span><span class="sxs-lookup"><span data-stu-id="6ae69-191">Review the request and import steps.</span></span> <span data-ttu-id="6ae69-192">Si le problème persiste, contactez l’administrateur de votre autorité de certification ou votre fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6ae69-192">If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="6ae69-193">Dans le **magasin personnel de certificats de l’ordinateur local**, cliquez avec le bouton droit sur le certificat que vous exportez, cliquez sur **toutes les tâches**, puis sur **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-193">In the **Certificates Personal store for the local computer**, right-click the certificate that you are exporting, click **All Tasks**, and then click **Export**.</span></span>

8.  <span data-ttu-id="6ae69-194">Dans l’Assistant exportation de certificat, cliquez sur **suivant**, sélectionnez **Oui, exporter la clé privée**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-194">In the Certificate Export Wizard, click **Next**, select **Yes, export the private key**, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ae69-195">Si la sélection est <STRONG>Oui, l’exportation de la clé privée</STRONG> n’est pas disponible, la clé privée associée à ce certificat n’a pas été marquée pour l’exportation.</span><span class="sxs-lookup"><span data-stu-id="6ae69-195">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export.</span></span> <span data-ttu-id="6ae69-196">Vous devrez demander de nouveau le certificat, en vous assurant que le certificat est marqué pour autoriser l’exportation de la clé privée avant de pouvoir poursuivre l’exportation.</span><span class="sxs-lookup"><span data-stu-id="6ae69-196">You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export.</span></span> <span data-ttu-id="6ae69-197">Contactez l’administrateur ou le fournisseur de votre autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="6ae69-197">Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="6ae69-198">Dans la boîte de dialogue Exporter les formats de fichiers, sélectionnez **échange d’informations personnelles – PKCS \# 12 (. PFX)** , puis sélectionnez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="6ae69-198">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="6ae69-199">Inclure tous les certificats dans le chemin d’accès de certification si possible</span><span class="sxs-lookup"><span data-stu-id="6ae69-199">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="6ae69-200">Exporter toutes les propriétés étendues</span><span class="sxs-lookup"><span data-stu-id="6ae69-200">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="6ae69-201">Lorsque vous exportez le certificat à partir d’un serveur Edge, ne sélectionnez pas <STRONG>Supprimer la clé privée si l’exportation réussit</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="6ae69-201">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>.</span></span> <span data-ttu-id="6ae69-202">Si vous sélectionnez cette option, vous devez importer le certificat et la clé privée sur ce serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="6ae69-202">Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>

10. <span data-ttu-id="6ae69-203">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-203">Click **Next**.</span></span>

11. <span data-ttu-id="6ae69-204">Tapez un mot de passe pour la clé privée, entrez de nouveau le mot de passe pour le confirmer, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-204">Type a password for the private key, type the password again to confirm, and then click **Next**.</span></span>

12. <span data-ttu-id="6ae69-205">Tapez un chemin d’accès et un nom de fichier pour le certificat exporté, à l’aide d’une extension de fichier. pfx.</span><span class="sxs-lookup"><span data-stu-id="6ae69-205">Type a path and file name for the exported certificate, using a file extension of .pfx.</span></span> <span data-ttu-id="6ae69-206">Le chemin d’accès doit être accessible à tous les autres serveurs Edge du pool ou être disponible pour le transport via un support amovible (par exemple, un lecteur flash USB).</span><span class="sxs-lookup"><span data-stu-id="6ae69-206">The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive.</span></span> <span data-ttu-id="6ae69-207">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-207">Click **Next**.</span></span>

13. <span data-ttu-id="6ae69-208">Consultez le résumé dans **fin de l’Assistant Exportation du certificat**, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-208">Review the summary in **Completing the Certificate Export Wizard**, and then click **Finish**.</span></span>

14. <span data-ttu-id="6ae69-209">Dans la boîte de dialogue exportation réussie, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-209">In the successful export dialog box, click **OK**.</span></span>

15. <span data-ttu-id="6ae69-210">Importez le fichier de certificat exporté vers les autres serveurs Edge en suivant les étapes décrites dans la procédure « pour importer le certificat pour l’interface externe du serveur Edge » plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="6ae69-210">Import the exported certificate file to the other Edge servers following the steps outlined in the “To import the certificate for the external interface of the Edge Server” procedure earlier in this topic.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="6ae69-211">Pour attribuer le certificat pour l’interface externe du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="6ae69-211">To assign the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="6ae69-212">Sur chaque serveur Edge, dans l’Assistant Déploiement, à côté de **étape 3 : demander, installer ou assigner les certificats**, cliquez sur **réexécuter**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-212">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="6ae69-213">Dans la page **tâches de certificats disponibles** , cliquez sur **affecter un certificat existant**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-213">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="6ae69-214">Dans la page **affectation de certificat** , cliquez sur certificat de serveur **Edge externe** et activez la case à cocher **utilisations de certificat avancées** .</span><span class="sxs-lookup"><span data-stu-id="6ae69-214">On the **Certificate Assignment** page, click **External Edge Certificate** and select the **Advanced Certificate Usages** check box.</span></span>

4.  <span data-ttu-id="6ae69-215">Sur la page **utilisations de certificat avancées** , activez toutes les cases à cocher pour attribuer le certificat à toutes les utilisations.</span><span class="sxs-lookup"><span data-stu-id="6ae69-215">On the **Advanced Certificate Usages** page, select all check boxes to assign the certificate for all usages.</span></span>

5.  <span data-ttu-id="6ae69-216">Sur la page **magasin de certificats** , sélectionnez le certificat public que vous avez demandé et importé pour l’interface externe du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="6ae69-216">On the **Certificate Store** page, select the public certificate that you requested and imported for the external interface of the Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ae69-217">Si le certificat que vous avez demandé et importé ne figure pas dans la liste, l’une des méthodes de dépannage consiste à vérifier que le nom de sujet et les autres noms de sujet du certificat répondent à toutes les exigences du certificat et, si vous avez importé manuellement le certificat et la chaîne de certificats au lieu d’utiliser les procédures précédentes, que le certificat se trouve dans le magasin de certificats approprié , et non l’utilisateur ou le magasin de certificats du service).</span><span class="sxs-lookup"><span data-stu-id="6ae69-217">If the certificate you requested and imported is not in the list, one of the trouble shooting methods is to verify that subject name and subject alternative names of the certificate meet all requirements for the certificate and, if you manually imported the certificate and certificate chain instead of using the preceding procedures, that the certificate is in the correct certificate store (the computer certificate store, not the user or service certificate store).</span></span>

    
    </div>

6.  <span data-ttu-id="6ae69-218">Sur la page Résumé de l' **affectation du certificat** , vérifiez vos paramètres, puis cliquez sur **suivant** pour affecter les certificats.</span><span class="sxs-lookup"><span data-stu-id="6ae69-218">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

7.  <span data-ttu-id="6ae69-219">Dans la page de fin de l’Assistant, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="6ae69-219">On the wizard completion page, click **Finish**.</span></span>

8.  <span data-ttu-id="6ae69-220">Après avoir utilisé cette procédure pour attribuer le certificat de périphérie, ouvrez le composant logiciel enfichable certificat sur chaque serveur, développez **certificats (ordinateur local)**, développez **personnel**, cliquez sur **certificats**, puis vérifiez dans le volet d’informations que le certificat est affiché.</span><span class="sxs-lookup"><span data-stu-id="6ae69-220">After using this procedure to assign the edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the certificate is listed.</span></span>

9.  <span data-ttu-id="6ae69-221">Si votre déploiement comprend plusieurs serveurs Edge, répétez cette procédure pour chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="6ae69-221">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

