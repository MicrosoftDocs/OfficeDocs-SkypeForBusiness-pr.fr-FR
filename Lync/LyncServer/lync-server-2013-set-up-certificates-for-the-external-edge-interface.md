---
title: 'Lync Server 2013 : Configuration des certificats pour l’interface Edge externe'
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
ms.openlocfilehash: c1c836191c19eeadd915d0263c89b52289f60fe9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a><span data-ttu-id="ac276-102">Configuration des certificats pour l’interface Edge externe pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac276-102">Set up certificates for the external edge interface for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac276-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ac276-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ac276-104">Lorsque vous exécutez l’Assistant certificat, assurez-vous que vous êtes connecté à l’aide d’un compte associé à un compte qui dispose des autorisations appropriées pour le type de modèle de certificat que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="ac276-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="ac276-105">Par défaut, une demande de certificat du serveur Lync utilise le modèle de certificat de serveur Web.</span><span class="sxs-lookup"><span data-stu-id="ac276-105">By default, a Lync Server certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="ac276-106">Si vous utilisez un compte membre du groupe RTCUniversalServerAdmins pour demander un certificat à l’aide de ce modèle, vérifiez que le groupe a été affecté aux autorisations d’inscription requises pour utiliser ce modèle.</span><span class="sxs-lookup"><span data-stu-id="ac276-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="ac276-107">Chaque serveur Edge nécessite un certificat public sur l’interface entre le réseau de périmètre et Internet, et le nom de l’autre sujet du certificat doit contenir les noms externes du service Edge d’accès et du service Edge de conférence Web entièrement noms de domaine qualifiés (FQDN).</span><span class="sxs-lookup"><span data-stu-id="ac276-107">Each Edge Server requires a public certificate on the interface between the perimeter network and the Internet, and the certificate’s subject alternative name must contain the external names of the Access Edge service and Web Conferencing Edge service fully qualified domain names (FQDNs).</span></span>

<span data-ttu-id="ac276-108">Pour plus d’informations sur ce problème et sur les autres exigences relatives aux certificats, voir [exigences relatives aux certificats pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="ac276-108">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="ac276-109">Pour obtenir une liste des autorités de certification publiques qui fournissent des certificats conformes à des exigences spécifiques en matière de certificats de communications unifiées et ayant un partenariat avec Microsoft pour vérifier qu’ils fonctionnent avec l’Assistant certificat de Lync Server 2013, voir l’article de la base de connaissances Microsoft 929395, « partenaires de certification de communications [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)unifiées pour Exchange Server » et de Communications Server».</span><span class="sxs-lookup"><span data-stu-id="ac276-109">For a list of public certification authorities (CAs) that provide certificates that comply with specific requirements for unified communications certificates and have partnered with Microsoft to ensure they work with the Lync Server 2013 Certificate Wizard, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a><span data-ttu-id="ac276-110">Configuration de certificats sur les interfaces externes</span><span class="sxs-lookup"><span data-stu-id="ac276-110">Configuring Certificates on the External Interfaces</span></span>

<span data-ttu-id="ac276-111">Pour configurer un certificat sur l’interface latérale externe sur un site, suivez les procédures décrites dans cette section pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ac276-111">To set up a certificate on the external edge interface at a site, use the procedures in this section to do the following:</span></span>

  - <span data-ttu-id="ac276-112">Créez une demande de certificat pour l’interface externe du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="ac276-112">Create the certificate request for the external interface of the Edge Server.</span></span>

  - <span data-ttu-id="ac276-113">Envoyez la demande à votre autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="ac276-113">Submit the request to your public CA.</span></span>

  - <span data-ttu-id="ac276-114">Importez le certificat pour l’interface externe de chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="ac276-114">Import the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="ac276-115">Attribuez le certificat pour l’interface externe de chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="ac276-115">Assign the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="ac276-116">Si votre déploiement inclut plusieurs serveurs Edge, exportez le certificat en même temps que sa clé privée, puis copiez-le sur l’autre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="ac276-116">If your deployment includes multiple Edge Servers, export the certificate along with its private key, and then copy it to the other Edge Servers.</span></span> <span data-ttu-id="ac276-117">Ensuite, pour chaque serveur Edge, importez-le et attribuez-le comme décrit précédemment.</span><span class="sxs-lookup"><span data-stu-id="ac276-117">Then, for each Edge Server, import it and assign it as previously described.</span></span> <span data-ttu-id="ac276-118">Répétez cette procédure pour chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="ac276-118">Repeat this procedure for each Edge Server.</span></span>

<span data-ttu-id="ac276-119">Vous pouvez demander des certificats publics directement auprès d’une autorité de certification (CA) publique (par exemple, à partir du site Web d’une autorité de certification publique).</span><span class="sxs-lookup"><span data-stu-id="ac276-119">You can request public certificates directly from a public certification authority (CA) (such as from the website of a public CA).</span></span> <span data-ttu-id="ac276-120">Les procédures décrites dans cette section utilisent l’Assistant Certificat pour la plupart des tâches de certificat.</span><span class="sxs-lookup"><span data-stu-id="ac276-120">The procedures in this section use the Certificate Wizard for most certificate tasks.</span></span> <span data-ttu-id="ac276-121">Si vous avez choisi de demander un certificat directement auprès d’une autorité de certification publique, vous devez modifier chaque procédure en fonction de la demande, du transport et de l’importation du certificat, ainsi que de l’importation de la chaîne de certificats.</span><span class="sxs-lookup"><span data-stu-id="ac276-121">If you chose to request a certificate directly from a public CA, then you will need to modify each procedure as appropriate to request, transport, and import the certificate and also to import the certificate chain.</span></span>

<span data-ttu-id="ac276-122">Lorsque vous demandez un certificat auprès d’une autorité de certification externe, les informations d’identification fournies doivent disposer de droits de demande de certificat de cette autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="ac276-122">When you request a certificate from an External CA, the credentials provided must have rights to request a certificate from that CA.</span></span> <span data-ttu-id="ac276-123">Chaque autorité de certification dispose d’une stratégie de sécurité qui définit les informations d’identification (c’est-à-dire, les noms d’utilisateurs et de groupes spécifiques) autorisées à demander, émettre, gérer ou lire des certificats.</span><span class="sxs-lookup"><span data-stu-id="ac276-123">Each CA has a security policy that defines which credentials (that is, specific user and group names) are allowed to request, issue, manage, or read certificates.</span></span>

<span data-ttu-id="ac276-124">Si vous décidez d’utiliser la console MMC (Microsoft Management Console) pour importer des certificats, vous devez les importer dans le magasin de certificats de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="ac276-124">If you decide to use the Certificates Microsoft Management Console (MMC) to import the certificate chain and certificate, you must import them to the certificate store for the computer.</span></span> <span data-ttu-id="ac276-125">Si vous les importez dans le magasin de certificats d’utilisateur ou de service, le certificat ne sera pas disponible pour attribution dans l’Assistant certificat de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ac276-125">If you import them to the user or service certificate store, the certificate will not be available for assignment in the Lync Server 2013 Certificate Wizard.</span></span>

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="ac276-126">Pour créer une demande de certificat pour l’interface externe du serveur de périphérie</span><span class="sxs-lookup"><span data-stu-id="ac276-126">To create the certificate request for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="ac276-127">Sur le serveur Edge, dans l’Assistant Déploiement, en regard de l' **étape 3 : demandez, installez ou attribuez des certificats**, cliquez de **nouveau sur exécuter**.</span><span class="sxs-lookup"><span data-stu-id="ac276-127">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ac276-128">Si votre organisation veut prendre en charge la connectivité de messagerie instantanée publique avec AOL, vous ne pouvez pas utiliser l’Assistant Déploiement de Lync Server pour demander le certificat.</span><span class="sxs-lookup"><span data-stu-id="ac276-128">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="ac276-129">À la place, suivez les étapes décrites dans la section « pour créer une demande de certificat pour l’interface externe du serveur Edge pour la prise en charge de la connectivité de messagerie instantanée publique avec AOL », plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="ac276-129">Instead, perform the steps in the “To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL” procedure later in this topic.</span></span><BR><span data-ttu-id="ac276-130">Si vous disposez de plusieurs serveurs Edge à un emplacement dans un pool, vous pouvez exécuter l’Assistant Certificat Lync Server 2013 sur l’un des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="ac276-130">If you have multiple Edge Servers in one location in a pool, you can run the Lync Server 2013 Certificate Wizard on any one of the Edge Servers.</span></span>

    
    </div>

2.  <span data-ttu-id="ac276-131">Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Créer une demande de certificat**.</span><span class="sxs-lookup"><span data-stu-id="ac276-131">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="ac276-132">Dans la page **demande de certificat** , cliquez sur certificat de **bord externe**.</span><span class="sxs-lookup"><span data-stu-id="ac276-132">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="ac276-133">Dans la page de **demande retardée ou immédiate** , activez la case à cocher **préparer la demande maintenant, puis l’envoyer plus tard** .</span><span class="sxs-lookup"><span data-stu-id="ac276-133">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="ac276-134">Dans la **page fichier de demande de certificat** , tapez le chemin d’accès complet et le nom du fichier dans lequel la demande doit être enregistrée (par exemple,\\c\_:\_CERT l’Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="ac276-134">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="ac276-135">Dans la page **spécifier un modèle de certificat secondaire** , pour utiliser un modèle autre que le modèle par défaut du serveur Web, activez la case à cocher utiliser un autre **modèle de certificat pour l’autorité de certification sélectionnée** .</span><span class="sxs-lookup"><span data-stu-id="ac276-135">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="ac276-136">Dans la page **paramètres de nom et de sécurité** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ac276-136">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="ac276-137">Dans **nom convivial**, tapez un nom d’affichage pour le certificat.</span><span class="sxs-lookup"><span data-stu-id="ac276-137">In **Friendly name**, type a display name for the certificate.</span></span>
    
      - <span data-ttu-id="ac276-138">En **longueur**, spécifiez la longueur en bits (en général, la valeur par défaut **2048**).</span><span class="sxs-lookup"><span data-stu-id="ac276-138">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
    
      - <span data-ttu-id="ac276-139">Vérifiez que la case à cocher **marquer le certificat en tant que clé publique en tant qu’export** est activée.</span><span class="sxs-lookup"><span data-stu-id="ac276-139">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="ac276-140">Dans la page informations sur l' **organisation** , tapez le nom de l’organisation et l’unité d’organisation (par exemple, une division ou un service).</span><span class="sxs-lookup"><span data-stu-id="ac276-140">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="ac276-141">Dans la page **informations géographiques** , spécifiez les informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="ac276-141">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="ac276-142">Sur la page nom de l’objet **/nom** de l’objet, les informations à remplir automatiquement par l’Assistant sont affichées.</span><span class="sxs-lookup"><span data-stu-id="ac276-142">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="ac276-143">Si d’autres noms d’objet sont nécessaires, vous pouvez les spécifier au cours des deux étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="ac276-143">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="ac276-144">Dans la page Configuration du protocole **SIP sur le nom de l’objet** , activez la case à cocher Domain pour ajouter un SIP. \<entrée\> sipdomain dans la liste noms de remplacement de l’objet.</span><span class="sxs-lookup"><span data-stu-id="ac276-144">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="ac276-145">Dans la page **configurez** d’autres noms d’objet, spécifiez d’autres noms d’objet obligatoires.</span><span class="sxs-lookup"><span data-stu-id="ac276-145">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

13. <span data-ttu-id="ac276-146">Dans la page Résumé de la **demande** , passez en revue les informations de certificat à utiliser pour générer la requête.</span><span class="sxs-lookup"><span data-stu-id="ac276-146">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="ac276-147">À la fin de l’exécution de la commande, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ac276-147">After the commands finish running, do the following:</span></span>
    
      - <span data-ttu-id="ac276-148">Pour afficher le journal de la demande de certificat, cliquez sur **afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="ac276-148">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="ac276-149">Pour remplir la demande de certificat, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="ac276-149">To complete the certificate request, click **Next**.</span></span>

15. <span data-ttu-id="ac276-150">Dans la page **fichier de demande de certificat** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ac276-150">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="ac276-151">Pour afficher le fichier de demande de signature de certificat généré (CSR), cliquez sur **Afficher**.</span><span class="sxs-lookup"><span data-stu-id="ac276-151">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="ac276-152">Pour fermer l’Assistant, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="ac276-152">To close the wizard, click **Finish**.</span></span>

16. <span data-ttu-id="ac276-153">Copiez le fichier de sortie à un emplacement dans lequel vous pouvez le renvoyer à l’autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="ac276-153">Copy the output file to a location where you can submit it to the public CA.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="ac276-154">Pour créer une demande de certificat pour l’interface externe du serveur de périphérie pour la prise en charge de la connectivité de messagerie instantanée publique avec AOL</span><span class="sxs-lookup"><span data-stu-id="ac276-154">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="ac276-155">Lorsque le modèle requis est disponible pour l’autorité de certification, utilisez la cmdlet Windows PowerShell suivante à partir du serveur de périphérie pour demander le certificat :</span><span class="sxs-lookup"><span data-stu-id="ac276-155">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate:</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="ac276-156">Le nom du certificat par défaut du modèle fourni dans Lync Server 2013 est serveur Web.</span><span class="sxs-lookup"><span data-stu-id="ac276-156">The default certificate name of the template provided in Lync Server 2013 is Web Server.</span></span> <span data-ttu-id="ac276-157">Spécifiez le \<nom\> du modèle uniquement si vous devez utiliser un modèle différent du modèle par défaut.</span><span class="sxs-lookup"><span data-stu-id="ac276-157">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ac276-158">Si votre organisation veut prendre en charge une connectivité de messagerie instantanée publique avec AOL, vous devez utiliser Windows PowerShell au lieu de l’Assistant Certificat pour demander que le certificat soit affecté au bord externe du service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="ac276-158">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="ac276-159">Ce problème est dû au fait que le modèle de serveur Web 2013 à l’aide de l’Assistant Création de certificat ne prend pas en charge la configuration EKU du client.</span><span class="sxs-lookup"><span data-stu-id="ac276-159">This is because the Lync Server 2013 Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="ac276-160">Avant d’utiliser Windows PowerShell pour créer le certificat, l’administrateur de l’autorité de certification doit créer et déployer un nouveau modèle qui prend en charge l’utilisation améliorée de l’utilisation du client.</span><span class="sxs-lookup"><span data-stu-id="ac276-160">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a><span data-ttu-id="ac276-161">Pour renvoyer une demande auprès d’une autorité de certification publique</span><span class="sxs-lookup"><span data-stu-id="ac276-161">To submit a request to a public certification authority</span></span>

1.  <span data-ttu-id="ac276-162">Ouvrez le fichier de sortie.</span><span class="sxs-lookup"><span data-stu-id="ac276-162">Open the output file.</span></span>

2.  <span data-ttu-id="ac276-163">Copiez et collez le contenu de la demande de signature de certificat (CSR).</span><span class="sxs-lookup"><span data-stu-id="ac276-163">Copy and paste the contents of the Certificate Signing Request (CSR).</span></span>

3.  <span data-ttu-id="ac276-164">Si vous y êtes invité, spécifiez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="ac276-164">If prompted, specify the following:</span></span>
    
      - <span data-ttu-id="ac276-165">**Microsoft** en tant que plateforme serveur.</span><span class="sxs-lookup"><span data-stu-id="ac276-165">**Microsoft** as the server platform.</span></span>
    
      - <span data-ttu-id="ac276-166">**IIS** en tant que version.</span><span class="sxs-lookup"><span data-stu-id="ac276-166">**IIS** as the version.</span></span>
    
      - <span data-ttu-id="ac276-167">**Serveur Web** comme type d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="ac276-167">**Web Server** as the usage type.</span></span>
    
      - <span data-ttu-id="ac276-168">**PKCS7** en tant que format de la réponse.</span><span class="sxs-lookup"><span data-stu-id="ac276-168">**PKCS7** as the response format.</span></span>

4.  <span data-ttu-id="ac276-169">Lorsque l’AC publique a vérifié vos informations, vous recevez un message électronique contenant un texte requis pour votre certificat.</span><span class="sxs-lookup"><span data-stu-id="ac276-169">When the public CA has verified your information, you will receive an email message containing text required for your certificate.</span></span>

5.  <span data-ttu-id="ac276-170">Copiez le texte du message électronique et enregistrez le contenu dans un fichier texte (. txt) sur votre ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="ac276-170">Copy the text from the email message and save the contents in a text file (.txt) on your local computer.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="ac276-171">Pour importer le certificat pour l’interface externe du serveur de périphérie</span><span class="sxs-lookup"><span data-stu-id="ac276-171">To import the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="ac276-172">Ouvrez une session en tant que membre du groupe Administrateurs sur le serveur Edge sur lequel vous avez créé la demande de certificat.</span><span class="sxs-lookup"><span data-stu-id="ac276-172">Log on as a member of the Administrators group to the same Edge Server on which you created the certificate request.</span></span>

2.  <span data-ttu-id="ac276-173">Dans l’Assistant Déploiement, dans la page **déploiement du serveur Edge** , en regard de l' **étape 3 : demander, installer ou affecter des certificats**, cliquez de nouveau sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="ac276-173">In the Deployment Wizard, on the **Deploy Edge Server** page, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

3.  <span data-ttu-id="ac276-174">Dans la page **tâches de certification disponibles** , cliquez sur **Importer un certificat à partir d’un fichier. p7b, pfx ou. cer**.</span><span class="sxs-lookup"><span data-stu-id="ac276-174">On the **Available Certificate Tasks** page, click **Import a certificate from a .p7b, pfx or .cer file**.</span></span>

4.  <span data-ttu-id="ac276-175">Sur la page **importer le certificat** , cliquez sur **Parcourir** pour rechercher et sélectionner le certificat que vous avez demandé pour l’interface externe du serveur Edge (ou bien tapez le chemin d’accès complet et le nom du fichier).</span><span class="sxs-lookup"><span data-stu-id="ac276-175">On the **Import Certificate** page, click **Browse** to locate and select the certificate that you requested for the external interface of the Edge Server (or, you can type the full path and file name).</span></span> <span data-ttu-id="ac276-176">Si le certificat contient une clé privée, sélectionnez le **fichier de certificat contient la clé privée du certificat** et tapez le mot de passe de la clé privée.</span><span class="sxs-lookup"><span data-stu-id="ac276-176">If the certificate contains a private key, select **Certificate file contains certificate’s private key** and type the password for the private key.</span></span> <span data-ttu-id="ac276-177">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ac276-177">Click **Next**.</span></span>

5.  <span data-ttu-id="ac276-178">Sur la page **importer le résumé du certificat** , examinez le résumé, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="ac276-178">On **Import Certificate Summary** page, review the summary and then click **Next**.</span></span>

6.  <span data-ttu-id="ac276-179">Sur l' **exécution des commandes**, examinez les résultats de l’importation, puis cliquez sur Afficher le journal pour **Afficher** d’autres informations si nécessaire, puis cliquez sur **Terminer** pour achever l’importation du certificat.</span><span class="sxs-lookup"><span data-stu-id="ac276-179">On **Executing Commands**, review the results of the import, click **View Log** for more information as needed, and then click **Finish** to complete the certificate import.</span></span>

7.  <span data-ttu-id="ac276-180">Si vous configurez un pool de serveurs Edge, exportez le certificat avec sa clé privée, comme indiqué dans la procédure « pour exporter le certificat avec la clé privée pour les serveurs Edge dans une liste » plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="ac276-180">If you are configuring an Edge Server pool, export the certificate with its private key as outlined in the “To export the certificate with the private key for Edge Servers in a pool” procedure later in this topic.</span></span> <span data-ttu-id="ac276-181">Copiez le fichier de certificat exporté vers les autres serveurs Edge, puis importez-le dans le magasin d’ordinateur sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="ac276-181">Copy the exported certificate file to the other Edge Servers, and import it into the computer store on each Edge Server.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="ac276-182">Pour exporter le certificat avec la clé privée pour les serveurs Edge dans un pool</span><span class="sxs-lookup"><span data-stu-id="ac276-182">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="ac276-183">Ouvrez une session en tant que membre du groupe Administrateurs sur le serveur Edge sur lequel vous avez importé le certificat.</span><span class="sxs-lookup"><span data-stu-id="ac276-183">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="ac276-184">Cliquez sur **Démarrer**, sur **exécuter**, puis tapez **MMC**.</span><span class="sxs-lookup"><span data-stu-id="ac276-184">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="ac276-185">Dans la console Microsoft Management Console (MMC), cliquez sur **fichier**, puis sur **Ajouter/supprimer un composant logiciel enfichable**.</span><span class="sxs-lookup"><span data-stu-id="ac276-185">In the Microsoft Management Console (MMC) console, click **File**, and then click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="ac276-186">Dans **Ajouter ou supprimer des composants logiciels enfichables**, cliquez sur **certificats**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="ac276-186">In **Add or Remove Snap-ins**, click **Certificates**, and then click **Add**.</span></span>

5.  <span data-ttu-id="ac276-187">Dans la boîte de dialogue **certificats** , sélectionnez **compte d’ordinateur**, cliquez sur **suivant**, sur **ordinateur local : (l’ordinateur sur lequel cette console s’exécute)** dans **Sélectionner un ordinateur**, cliquez sur **Terminer** , puis sur **OK** pour terminer la configuration de la console MMC.</span><span class="sxs-lookup"><span data-stu-id="ac276-187">In the **Certificates** dialog box, select **Computer account**, click **Next**, select **Local computer: (the computer this console is running on)** in **Select Computer**, click **Finish** and then click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="ac276-188">Double-cliquez sur **certificats (ordinateur local)** pour développer les magasins de certificats, double-cliquez sur **personnel**, puis double-cliquez sur **certificats**.</span><span class="sxs-lookup"><span data-stu-id="ac276-188">Double-click **Certificates (Local Computer)** to expand the certificate stores, double-click **Personal**, and then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ac276-189">S’il n’y a aucun certificat dans le magasin personnel de certificats de l’ordinateur local, il n’existe aucune clé privée associée au certificat importé.</span><span class="sxs-lookup"><span data-stu-id="ac276-189">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported.</span></span> <span data-ttu-id="ac276-190">Passez en revue les étapes de demande et d’importation.</span><span class="sxs-lookup"><span data-stu-id="ac276-190">Review the request and import steps.</span></span> <span data-ttu-id="ac276-191">Si le problème persiste, contactez votre administrateur ou fournisseur de l’autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="ac276-191">If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="ac276-192">Dans le **magasin personnel de certificats de l’ordinateur local**, cliquez avec le bouton droit sur le certificat que vous exportez, cliquez sur **toutes les tâches**, puis cliquez sur **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="ac276-192">In the **Certificates Personal store for the local computer**, right-click the certificate that you are exporting, click **All Tasks**, and then click **Export**.</span></span>

8.  <span data-ttu-id="ac276-193">Dans l’Assistant exportation de certificat, cliquez sur **suivant**, sélectionnez **Oui, exportez la clé privée**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="ac276-193">In the Certificate Export Wizard, click **Next**, select **Yes, export the private key**, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ac276-194">Si la sélection est <STRONG>Oui, exporter la clé privée</STRONG> n’est pas disponible, la clé privée associée à ce certificat n’est pas marquée pour l’exportation.</span><span class="sxs-lookup"><span data-stu-id="ac276-194">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export.</span></span> <span data-ttu-id="ac276-195">Vous devez demander à nouveau le certificat, en veillant à ce que le certificat soit marqué pour autoriser l’exportation de la clé privée avant de poursuivre l’exportation.</span><span class="sxs-lookup"><span data-stu-id="ac276-195">You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export.</span></span> <span data-ttu-id="ac276-196">Contactez votre administrateur ou fournisseur de l’autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="ac276-196">Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="ac276-197">Dans la boîte de dialogue Exporter les formats de fichier, sélectionnez **échange\#d’informations personnelles – PKCS 12 (. PFX)** , puis sélectionnez les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="ac276-197">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="ac276-198">Incluez tous les certificats dans le chemin de certification, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="ac276-198">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="ac276-199">Exporter toutes les propriétés étendues</span><span class="sxs-lookup"><span data-stu-id="ac276-199">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="ac276-200">Lorsque vous exportez le certificat à partir d’un serveur Edge, ne sélectionnez pas <STRONG>Supprimer la clé privée si l’exportation est réussie</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ac276-200">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>.</span></span> <span data-ttu-id="ac276-201">La sélection de cette option nécessite l’importation du certificat et de la clé privée vers ce serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="ac276-201">Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>

10. <span data-ttu-id="ac276-202">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ac276-202">Click **Next**.</span></span>

11. <span data-ttu-id="ac276-203">Tapez un mot de passe pour la clé privée, tapez à nouveau le mot de passe pour le confirmer, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="ac276-203">Type a password for the private key, type the password again to confirm, and then click **Next**.</span></span>

12. <span data-ttu-id="ac276-204">Tapez un chemin d’accès et un nom de fichier avec l’extension .pfx pour le certificat exporté.</span><span class="sxs-lookup"><span data-stu-id="ac276-204">Type a path and file name for the exported certificate, using a file extension of .pfx.</span></span> <span data-ttu-id="ac276-205">Le chemin d’accès doit être accessible à tous les autres serveurs de périphérie du pool ou disponible pour le transport par le biais de médias amovibles (par exemple, un lecteur flash USB).</span><span class="sxs-lookup"><span data-stu-id="ac276-205">The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive.</span></span> <span data-ttu-id="ac276-206">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ac276-206">Click **Next**.</span></span>

13. <span data-ttu-id="ac276-207">Passez en revue le résumé pour **terminer l’Assistant exportation de certificat**, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="ac276-207">Review the summary in **Completing the Certificate Export Wizard**, and then click **Finish**.</span></span>

14. <span data-ttu-id="ac276-208">Dans la boîte de dialogue exportation réussie, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ac276-208">In the successful export dialog box, click **OK**.</span></span>

15. <span data-ttu-id="ac276-209">Importez le fichier de certificat exporté vers les autres serveurs de périmètre en suivant les étapes décrites dans la procédure « importer le certificat pour l’interface externe de la section serveur Edge » plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="ac276-209">Import the exported certificate file to the other Edge servers following the steps outlined in the “To import the certificate for the external interface of the Edge Server” procedure earlier in this topic.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="ac276-210">Pour attribuer le certificat pour l’interface externe du serveur de périphérie</span><span class="sxs-lookup"><span data-stu-id="ac276-210">To assign the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="ac276-211">Sur chaque serveur Edge, dans l’Assistant Déploiement, en regard de l' **étape 3 : demandez, installez ou attribuez des certificats**, cliquez de **nouveau sur exécuter**.</span><span class="sxs-lookup"><span data-stu-id="ac276-211">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="ac276-212">Dans la page **tâches de certification disponibles** , cliquez sur **attribuer un certificat existant**.</span><span class="sxs-lookup"><span data-stu-id="ac276-212">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="ac276-213">Dans la page **affectation de certificat** , cliquez sur certificat de **périphérie externe** , puis activez la case à cocher **Utilisation avancée des certificats** .</span><span class="sxs-lookup"><span data-stu-id="ac276-213">On the **Certificate Assignment** page, click **External Edge Certificate** and select the **Advanced Certificate Usages** check box.</span></span>

4.  <span data-ttu-id="ac276-214">Sur la page **Utilisation avancée du certificat** , activez toutes les cases à cocher pour affecter le certificat à toutes les utilisations.</span><span class="sxs-lookup"><span data-stu-id="ac276-214">On the **Advanced Certificate Usages** page, select all check boxes to assign the certificate for all usages.</span></span>

5.  <span data-ttu-id="ac276-215">Dans la page **magasin de certificats** , sélectionnez le certificat public que vous avez demandé et importé pour l’interface externe du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="ac276-215">On the **Certificate Store** page, select the public certificate that you requested and imported for the external interface of the Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ac276-216">Si le certificat que vous avez demandé et importé ne figure pas dans la liste, l’une des méthodes de tournage peut consister à vérifier que le nom de l’objet et le nom de l’objet du certificat répondent à toutes les conditions requises pour le certificat et, si vous avez importé manuellement le certificat et chaîne de certificats au lieu d’utiliser les procédures précédentes, que le certificat se trouve dans le magasin de certificats approprié (le magasin de certificats de l’ordinateur, et non pas le magasin de certificats d’utilisateur ou de service).</span><span class="sxs-lookup"><span data-stu-id="ac276-216">If the certificate you requested and imported is not in the list, one of the trouble shooting methods is to verify that subject name and subject alternative names of the certificate meet all requirements for the certificate and, if you manually imported the certificate and certificate chain instead of using the preceding procedures, that the certificate is in the correct certificate store (the computer certificate store, not the user or service certificate store).</span></span>

    
    </div>

6.  <span data-ttu-id="ac276-217">Dans la page **Résumé des affectations de certificat** , passez en revue vos paramètres, puis cliquez sur **suivant** pour attribuer les certificats.</span><span class="sxs-lookup"><span data-stu-id="ac276-217">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

7.  <span data-ttu-id="ac276-218">Dans la page de fin de l’Assistant, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="ac276-218">On the wizard completion page, click **Finish**.</span></span>

8.  <span data-ttu-id="ac276-219">Lorsque vous utilisez cette procédure pour attribuer le certificat de bord, ouvrez le composant logiciel enfichable Certificats sur chaque serveur, développez **certificats (ordinateur local)**, **personnel**, cliquez sur **certificats**, puis vérifiez dans le volet d’informations que le certificat est répertorié.</span><span class="sxs-lookup"><span data-stu-id="ac276-219">After using this procedure to assign the edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the certificate is listed.</span></span>

9.  <span data-ttu-id="ac276-220">Si votre déploiement inclut plusieurs serveurs Edge, répétez cette procédure pour chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="ac276-220">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

