---
title: Demander et configurer un certificat pour votre proxy HTTP inverse
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c380cb67e1e156bef616f81ce0c42f699b472d8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a><span data-ttu-id="4f8d8-102">Demander et configurer un certificat pour votre proxy HTTP inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f8d8-102">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f8d8-103">_**Dernière modification de la rubrique :** 2014-02-14_</span><span class="sxs-lookup"><span data-stu-id="4f8d8-103">_**Topic Last Modified:** 2014-02-14_</span></span>

<span data-ttu-id="4f8d8-104">Vous devez installer le certificat de l’autorité de certification (CA) racine sur le serveur exécutant Microsoft Forefront Threat Management Gateway 2010 ou IIS ARR pour l’infrastructure de l’autorité de certification qui a émis les certificats de serveur sur les serveurs internes exécutant Microsoft Lync. Serveur 2013.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-104">You need to install the root certification authority (CA) certificate on the server running Microsoft Forefront Threat Management Gateway 2010 or IIS ARR for the CA infrastructure that issued the server certificates to the internal servers running Microsoft Lync Server 2013.</span></span>

<span data-ttu-id="4f8d8-p101">Vous devez également installer un certificat de serveur web public sur votre serveur proxy inverse. Les autres noms de sujet de ce certificat doivent contenir les noms de domaine complets externes publiés de chaque pool hébergeant les utilisateurs activés pour l’accès à distance, ainsi que les noms de domaine complets externes de tous les directeurs ou pools directeurs qui seront utilisés dans cette infrastructure Edge. L’autre nom de sujet doit aussi contenir l’URL simple de réunion, l’URL simple de conférence rendez-vous et, si vous déployez des applications mobiles et prévoyez d’utiliser la découverte automatique, l’URL du service de découverte automatique externe, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-p101">You also must install a public web server certificate on your reverse proxy server. This certificate’s subject alternative names should contain the published external fully qualified domain names (FQDNs) of each pool that is home to users enabled for remote access, and the external FQDNs of all Directors or Director pools that will be used within that Edge infrastructure. The subject alternative name must also contain the meeting simple URL, the dial-in simple URL, and, if you are deploying mobile applications and plan to use automatic discovery, the external Autodiscover Service URL as shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="4f8d8-108">Valeur</span><span class="sxs-lookup"><span data-stu-id="4f8d8-108">Value</span></span></th>
<th><span data-ttu-id="4f8d8-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="4f8d8-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f8d8-110">Nom du sujet</span><span class="sxs-lookup"><span data-stu-id="4f8d8-110">Subject name</span></span></p></td>
<td><p><span data-ttu-id="4f8d8-111">Nom de domaine complet du pool</span><span class="sxs-lookup"><span data-stu-id="4f8d8-111">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="4f8d8-112">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4f8d8-112">webext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f8d8-113">Autre nom du sujet</span><span class="sxs-lookup"><span data-stu-id="4f8d8-113">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="4f8d8-114">Nom de domaine complet du pool</span><span class="sxs-lookup"><span data-stu-id="4f8d8-114">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="4f8d8-115">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4f8d8-115">webext.contoso.com</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="4f8d8-116">Le nom du sujet doit aussi être présent dans l’autre nom de sujet.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-116">The subject name must also be present in the subject alternative name.</span></span>

</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f8d8-117">Autre nom du sujet</span><span class="sxs-lookup"><span data-stu-id="4f8d8-117">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="4f8d8-118">Services Web de directeur facultatifs (si Director est déployé)</span><span class="sxs-lookup"><span data-stu-id="4f8d8-118">Optional Director Web Services (if Director is deployed)</span></span></p></td>
<td><p><span data-ttu-id="4f8d8-119">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4f8d8-119">webdirext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f8d8-120">Autre nom du sujet</span><span class="sxs-lookup"><span data-stu-id="4f8d8-120">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="4f8d8-121">URL simple de réunion</span><span class="sxs-lookup"><span data-stu-id="4f8d8-121">Meeting simple URL</span></span></p>



> [!NOTE]
> <span data-ttu-id="4f8d8-p102">Toutes les URL simples de réunion doivent se trouver dans l’autre nom de sujet. Chaque domaine SIP doit comporter au moins une URL simple de réunion active.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-p102">All meeting simple URLs must be in the subject alternative name. Each SIP domain must have at least one active meeting simple URL.</span></span>

</td>
<td><p><span data-ttu-id="4f8d8-124">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4f8d8-124">meet.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f8d8-125">Autre nom du sujet</span><span class="sxs-lookup"><span data-stu-id="4f8d8-125">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="4f8d8-126">URL simple Dial-in</span><span class="sxs-lookup"><span data-stu-id="4f8d8-126">Dial-in simple URL</span></span></p></td>
<td><p><span data-ttu-id="4f8d8-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4f8d8-127">dialin.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f8d8-128">Autre nom du sujet</span><span class="sxs-lookup"><span data-stu-id="4f8d8-128">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="4f8d8-129">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="4f8d8-129">Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="4f8d8-130">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4f8d8-130">officewebapps01.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f8d8-131">Autre nom du sujet</span><span class="sxs-lookup"><span data-stu-id="4f8d8-131">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="4f8d8-132">URL du service de découverte automatique externe</span><span class="sxs-lookup"><span data-stu-id="4f8d8-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="4f8d8-133">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4f8d8-133">lyncdiscover.contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="4f8d8-134">Si vous utilisez également Microsoft Exchange Server, vous devrez également configurer des règles de proxy inverse pour les URL de services Web et de découverte automatique Exchange.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-134">If you are also using Microsoft Exchange Server you will also need to configure reverse proxy rules for the Exchange autodiscover and web services URLs.</span></span>

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="4f8d8-135">Si votre déploiement interne se compose de plusieurs serveurs Standard Edition ou pools frontaux, vous devez configurer les règles de publication web pour chaque nom de domaine complet (FQDN) externe de la batterie de serveurs web. En outre, soit vous avez besoin d’un certificat et d’un port d’écoute web pour chacun, soit vous devez obtenir un certificat dont l’autre nom de sujet contient les noms utilisés par tous les pools, l’affecter à un port d’écoute web et le partager entre plusieurs règles de publication web.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-135">If your internal deployment consists of more than one Standard Edition server or Front End pool, you must configure web publishing rules for each external web farm FQDN and you will either need a certificate and web listener for each, or you must obtain a certificate whose subject alternative name contains the names used by all of the pools, assign it to a web listener, and share it among multiple web publishing rules.</span></span>



</div>

<div>

## <a name="create-a-certificate-request"></a><span data-ttu-id="4f8d8-136">Créer une demande de certificat</span><span class="sxs-lookup"><span data-stu-id="4f8d8-136">Create a Certificate Request</span></span>

<span data-ttu-id="4f8d8-137">Vous créez une demande de certificat sur le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-137">You create a certificate request on the reverse proxy.</span></span> <span data-ttu-id="4f8d8-138">Vous créez une demande sur un autre ordinateur, mais vous devez exporter le certificat signé avec la clé privée et l’importer sur le proxy inverse une fois que vous l’avez reçu de l’autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-138">You create a request on another computer, but you must export the signed certificate with the private key and import it onto the reverse proxy once you have received it from the public certification authority.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="4f8d8-139">Une demande de certificat ou une demande de signature de certificat (CSR) est une demande adressée à une autorité de certification publique (CA) approuvée pour valider et signer la clé publique de l’ordinateur demandeur.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-139">A certificate request or a certificate signing request (CSR) is a request to a trusted public certification authority (CA) to validate and sign the requesting computer’s public key.</span></span> <span data-ttu-id="4f8d8-140">Lorsqu’un certificat est généré, une clé publique et une clé privée sont créées.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-140">When a certificate is generated, a public key and a private key are created.</span></span> <span data-ttu-id="4f8d8-141">Seule la clé publique est partagée et signée.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-141">Only the public key is shared and signed.</span></span> <span data-ttu-id="4f8d8-142">Comme son nom l’indique, la clé publique est mise à la disposition de toute demande publique.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-142">As the name implies, the public key is made available to any public request.</span></span> <span data-ttu-id="4f8d8-143">La clé publique est destinée à être utilisée par les clients, les serveurs et d’autres demandeurs qui doivent échanger des informations en toute sécurité et valider l’identité d’un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-143">The public key is for use by clients, servers and other requesters that need to exchange information securely and validate a computer’s identity.</span></span> <span data-ttu-id="4f8d8-144">La clé privée est gardée sécurisée et n’est utilisée que par l’ordinateur qui a créé la paire de clés pour déchiffrer les messages chiffrés avec sa clé publique.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-144">The private key is kept secured and is used only by the computer that created the key pair to decrypt messages encrypted with its public key.</span></span> <span data-ttu-id="4f8d8-145">La clé privée peut être utilisée à d’autres fins.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-145">The private key can be used for other purposes.</span></span> <span data-ttu-id="4f8d8-146">Pour les rôles de proxy inverse, le chiffrement des données est l’utilisation principale.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-146">For reverse proxy purposes, data encipherment is the primary use.</span></span> <span data-ttu-id="4f8d8-147">Accessoire, l’authentification par certificat au niveau de la clé de certificat est une autre utilisation et est limitée uniquement à la validation qu’un demandeur a la clé publique de l’ordinateur, ou que l’ordinateur pour lequel vous avez une clé publique est effectivement l’ordinateur qu’il prétend être.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-147">Secondarily, the certificate authentication at the certificate key level is another use, and is limited only to validation that a requester has the computer’s public key, or that the computer that you have a public key for is actually the computer that it claims to be.</span></span>



</div>

<div>


> [!TIP]
> <span data-ttu-id="4f8d8-148">Si vous planifiez les certificats de votre serveur Edge et vos certificats de proxy inverse en même temps, vous devez remarquer qu’il existe beaucoup de similitudes entre les deux exigences de certificat.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-148">If you plan your Edge Server certificates and your reverse proxy certificates at the same time, you should notice that there is a great deal of similarity between the two certificate requirements.</span></span> <span data-ttu-id="4f8d8-149">Lorsque vous configurez et demandez votre certificat de serveur Edge, combinez le serveur Edge et les autres noms de sujet de proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-149">When you configure and request your Edge Server certificate, combine the Edge Server and the reverse proxy subject alternative names.</span></span> <span data-ttu-id="4f8d8-150">Vous pouvez utiliser le même certificat pour votre proxy inverse si vous exportez le certificat et la clé privée, puis copiez le fichier exporté vers le proxy inverse, puis importez le certificat/la paire de clés et attribuez-le selon vos besoins dans les procédures à venir.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-150">You can use the same certificate for your reverse proxy if you export the certificate and the private key and copy the exported file to the reverse proxy and then import the certificate/key pair and assign it as needed in the upcoming procedures.</span></span> <span data-ttu-id="4f8d8-151">Reportez-vous à la rubrique Certificate Requirements for the Edge Server&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">plan for Edge Server Certificates in Lync Server 2013</A> et The inversion proxy <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Certificate Summary-Reverse Proxy in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-151">Refer to the certificate requirements for the Edge Server&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan for Edge Server certificates in Lync Server 2013</A> and the reverse proxy <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Certificate summary - Reverse proxy in Lync Server 2013</A>.</span></span> <span data-ttu-id="4f8d8-152">Veillez à créer le certificat avec une clé privée exportable.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-152">Make sure that you create the certificate with an exportable private key.</span></span> <span data-ttu-id="4f8d8-153">La création du certificat et de la demande de certificat avec une clé privée exportable est requise pour les serveurs Edge regroupés, c’est une pratique normale et l’Assistant certificat de l’Assistant Déploiement de Lync Server pour le serveur Edge vous permet de définir l’indicateur <STRONG>Make Private Key exportable</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="4f8d8-153">Creating the certificate and certificate request with an exportable private key is required for pooled Edge Servers, so this is a normal practice and the Certificate Wizard in the Lync Server Deployment Wizard for the Edge Server will allow you to set the <STRONG>Make private key exportable</STRONG> flag.</span></span> <span data-ttu-id="4f8d8-154">Une fois que vous avez reçu la demande de certificat de l’autorité de certification publique, vous exportez le certificat et la clé privée.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-154">Once you receive the certificate request back from the public certification authority, you will export the certificate and the private key.</span></span> <span data-ttu-id="4f8d8-155">Reportez-vous à la section « pour exporter le certificat avec la clé privée pour les serveurs Edge dans un pool » dans la rubrique <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">set up Certificates for the external Edge interface for Lync Server 2013</A> pour plus d’informations sur la procédure de création et d’exportation de votre certificat avec une clé privée.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-155">See the section “To export the certificate with the private key for Edge Servers in a pool” in the topic <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Set up certificates for the external edge interface for Lync Server 2013</A> for details on how to create and export your certificate with a private key.</span></span> <span data-ttu-id="4f8d8-156">L’extension du certificat doit être de type <STRONG>. pfx</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-156">The extension of the certificate should be of type <STRONG>.pfx</STRONG>.</span></span>



</div>

<span data-ttu-id="4f8d8-157">Pour générer une demande de signature de certificat sur l’ordinateur sur lequel le certificat et la clé privée seront affectés, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4f8d8-157">To generate a certificate signing request on the computer where the certificate and private key will be assigned, you do the following:</span></span>

<span data-ttu-id="4f8d8-158">**Création d’une demande de signature de certificat**</span><span class="sxs-lookup"><span data-stu-id="4f8d8-158">**Creating a certificate signing request**</span></span>

1.  <span data-ttu-id="4f8d8-159">Ouvrez la console MMC (Microsoft Management Console) et ajoutez le composant logiciel enfichable Certificats, sélectionnez **ordinateurs**, puis développez **personnel**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-159">Open the Microsoft Management Console (MMC) and add the Certificates snap-in and select **Computers**, then expand **Personal**.</span></span> <span data-ttu-id="4f8d8-160">Pour plus d’informations sur la création d’une console certificats dans la console MMC (Microsoft Management Console [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616)), reportez-vous à la rubrique.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-160">For details on how to create a certificates console in the Microsoft Management Console (MMC), see [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616).</span></span>

2.  <span data-ttu-id="4f8d8-161">Cliquez avec le bouton droit sur **certificats**, cliquez sur **toutes les tâches**, puis sur **opérations avancées**, cliquez sur **créer une demande personnalisée**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-161">Right-click **Certificates**, click **All Tasks**, click **Advanced Operations**, click **Create Custom Request**.</span></span>

3.  <span data-ttu-id="4f8d8-162">Dans la page d' **enregistrement du certificat** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-162">On the **Certificate Enrollment** page, click **Next**.</span></span>

4.  <span data-ttu-id="4f8d8-163">Dans la page **Sélectionner une stratégie d’enregistrement de certificat** sous **demande personnalisée**, sélectionnez **continuer sans la stratégie d’enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-163">On the **Select Certificate Enrollment Policy** page under **Custom Request**, select **Proceed without enrollment policy**.</span></span> <span data-ttu-id="4f8d8-164">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-164">Click **Next**.</span></span>

5.  <span data-ttu-id="4f8d8-165">Sur la page **demande personnalisée** , pour la clé héritée de sélection de **modèle** **(aucun modèle)**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-165">On the **Custom Request** page, for **Template** select **(No template) Legacy key**.</span></span> <span data-ttu-id="4f8d8-166">Sauf indication contraire de votre fournisseur de certificats, laissez la case à cocher **Supprimer les extensions par défaut** désactivée et la sélection **format de demande** sur \*\* \#PKCS 10\*\*.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-166">Unless otherwise directed by your certificate provider, leave **Suppress default extensions** unchecked and the **Request format** selection on **PKCS \#10**.</span></span> <span data-ttu-id="4f8d8-167">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-167">Click **Next**.</span></span>

6.  <span data-ttu-id="4f8d8-168">Sur la page informations sur le **certificat** , cliquez sur **Détails**, puis sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-168">On the **Certificate Information** page, click **Details**, then click **Properties**.</span></span>

7.  <span data-ttu-id="4f8d8-169">Dans la page **Propriétés du certificat** , sous l’onglet **général** , dans le champ **nom convivial** , tapez un nom pour ce certificat.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-169">On the **Certificate Properties** page on the **General** tab in the **Friendly Name** field, type a name for this certificate.</span></span> <span data-ttu-id="4f8d8-170">Si vous le souhaitez, tapez une description dans le champ **Description** .</span><span class="sxs-lookup"><span data-stu-id="4f8d8-170">Optionally, type a description in the **Description** field.</span></span> <span data-ttu-id="4f8d8-171">Le nom convivial et la description sont généralement utilisés par l’administrateur pour identifier l’objectif du certificat, par exemple l' **écouteur de proxy inverse pour Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-171">The Friendly Name and description are typically used by the Administrator to identify what the certificate purpose is, such as **Reverse Proxy Listener for Lync Server**.</span></span>

8.  <span data-ttu-id="4f8d8-172">Sélectionnez l’onglet **sujet** . Sous **nom du sujet** pour le **type**, sélectionnez **nom commun** pour le type de nom d’objet.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-172">Select the **Subject** tab. Under **Subject name** for the **Type**, select **Common name** for the Subject name type.</span></span> <span data-ttu-id="4f8d8-173">Pour la **valeur**, tapez le nom de l’objet que vous allez utiliser pour le proxy inverse, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-173">For the **Value**, type the subject name that you will use for the reverse proxy, and then click **Add**.</span></span> <span data-ttu-id="4f8d8-174">Dans l’exemple fourni dans le tableau de cette rubrique, le nom de l’objet est webext.contoso.com et sera tapé dans le champ de valeur du nom de l’objet.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-174">In the example provided in the table in this topic, the subject name is webext.contoso.com and would be typed into the Value field for the Subject name.</span></span>

9.  <span data-ttu-id="4f8d8-175">Sous **autre nom**, dans l’onglet **objet** , sélectionnez **DNS** dans la liste déroulante pour **type**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-175">On the **Subject** tab under **Alternative name**, select **DNS** from the drop down for **Type**.</span></span> <span data-ttu-id="4f8d8-176">Pour chaque autre nom de sujet défini dont vous avez besoin sur le certificat, tapez le nom de domaine complet, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-176">For each defined subject alternative name that you require on the certificate, type the fully qualified domain name, then click **Add**.</span></span> <span data-ttu-id="4f8d8-177">Par exemple, dans le tableau, il existe trois autres noms de sujet, meet.contoso.com, dialin.contoso.com et lyncdiscover.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-177">For example, in the table there are three subject alternative names, meet.contoso.com, dialin.contoso.com, and lyncdiscover.contoso.com.</span></span> <span data-ttu-id="4f8d8-178">Dans le champ **valeur** , tapez Meet.contoso.com, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-178">In the **Value** field, type meet.contoso.com, then click **Add**.</span></span> <span data-ttu-id="4f8d8-179">Répétez l’opération pour chaque autre nom de sujet que vous devez définir.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-179">Repeat for each subject alternative names that you need to define.</span></span>

10. <span data-ttu-id="4f8d8-180">Sur la page **Propriétés du certificat** , cliquez sur l’onglet **Extensions** . Sur cette page, vous allez définir les rôles de clé de chiffrement dans l' **utilisation** de la clé et l’utilisation de la clé étendue dans **l’utilisation étendue de la clé (stratégies d’application)**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-180">On the **Certificate Properties** page, click the **Extensions** tab. On this page, you will define the cryptographic key purposes in **Key usage** and the extended key usage in **Extended Key Usage (application policies)**.</span></span>

11. <span data-ttu-id="4f8d8-181">Cliquez sur la flèche d' **utilisation clé** pour afficher les **options disponibles**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-181">Click the **Key usage** arrow to show the **Available options**.</span></span> <span data-ttu-id="4f8d8-182">Sous options disponibles, cliquez sur **signature numérique**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-182">Under Available options, click **Digital signature**, then click **Add**.</span></span> <span data-ttu-id="4f8d8-183">Cliquez sur **chiffrement**de la clé, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-183">Click **Key encipherment**, then click **Add**.</span></span> <span data-ttu-id="4f8d8-184">Si la case à cocher **appliquer ces utilisations de clés critiques** n’est pas cochée, activez la case à cocher.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-184">If the checkbox for **Make these key usages critical** is unchecked, select the checkbox.</span></span>

12. <span data-ttu-id="4f8d8-185">Cliquez sur la flèche utilisation de la **clé étendue (stratégies d’application)** pour afficher les **options disponibles**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-185">Click the **Extended Key Usage (application policies)** arrow to show the **Available options**.</span></span> <span data-ttu-id="4f8d8-186">Sous options disponibles, cliquez sur **authentification serveur**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-186">Under Available options, click **Server Authentication**, then click **Add**.</span></span> <span data-ttu-id="4f8d8-187">Cliquez sur **authentification client**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-187">Click **Client Authentication**, then click **Add**.</span></span> <span data-ttu-id="4f8d8-188">Si la case à cocher **activer les utilisations de la clé étendue critique** est activée, désélectionnez la case à cocher.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-188">If the check box for **Make the Extended Key Usages critical** is checked, unselect the checkbox.</span></span> <span data-ttu-id="4f8d8-189">Contrairement à la case à cocher utilisation de la clé (qui doit être vérifiée), vous devez vous assurer que la case à cocher utilisation étendue de la clé n’est pas activée.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-189">Contrary to the Key usage checkbox (which must be checked) you must be sure that the Extended Key Usage checkbox is not checked.</span></span>

13. <span data-ttu-id="4f8d8-190">Sur la page **Propriétés du certificat** , cliquez sur l’onglet **clé privée** . \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4f8d8-190">On the **Certificate Properties** page, click the **Private Key** tab. Click the **Key options** arrow.</span></span> <span data-ttu-id="4f8d8-191">Pour **taille**de la clé, sélectionnez **2048** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-191">For **Key size**, select **2048** from the drop down.</span></span> <span data-ttu-id="4f8d8-192">Si vous générez ce couple de clés et CSR sur un ordinateur autre que le proxy inverse auquel ce certificat est destiné, sélectionnez **définir la clé privée exportable**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-192">If you are generating this key pair and CSR on a computer other than the reverse proxy that this certificate is intended for, select **Make private key exportable**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="caution" alt="security" /><span data-ttu-id="4f8d8-194">Note de sécurité :</span><span class="sxs-lookup"><span data-stu-id="4f8d8-194">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="4f8d8-195">La sélection d' <strong>une clé privée exportable</strong> est généralement conseillée lorsque vous avez plusieurs proxys inverses dans une batterie de serveurs, car vous copiez le certificat et la clé privée sur chaque ordinateur de la batterie de serveurs.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-195">Selecting <strong>Make a private key exportable</strong> is generally advised when you have more than one reverse proxy in a farm because you will copy the certificate and the private key to each machine in the farm.</span></span> <span data-ttu-id="4f8d8-196">Si vous autorisez une clé privée exportable, vous devez vous préoccuper du certificat et de l’ordinateur sur lequel il est généré.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-196">If you do allow for an exportable private key, you must take extra care with the certificate and the computer that it is generated on.</span></span> <span data-ttu-id="4f8d8-197">La clé privée, si elle est compromise, rend le certificat inutile et expose potentiellement l’ordinateur ou les ordinateurs à l’accès externe et aux autres failles de sécurité.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-197">The private key, if compromised, will render the certificate useless as well as potentially expose the computer or computers to external access and other security vulnerabilities.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. <span data-ttu-id="4f8d8-198">Sous l’onglet **clé privée** , cliquez sur la flèche **type de touche** .</span><span class="sxs-lookup"><span data-stu-id="4f8d8-198">On the **Private Key** tab, click the **Key type** arrow.</span></span> <span data-ttu-id="4f8d8-199">Sélectionnez l’option **Exchange** .</span><span class="sxs-lookup"><span data-stu-id="4f8d8-199">Select the **Exchange** option.</span></span>

15. <span data-ttu-id="4f8d8-200">Cliquez sur **OK** pour enregistrer les **Propriétés de certificat** que vous avez définies.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-200">Click **OK** to save the **Certificate Properties** that you have set.</span></span>

16. <span data-ttu-id="4f8d8-201">Dans la page d' **enregistrement du certificat** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-201">On the **Certificate Enrollment** page, click **Next**.</span></span>

17. <span data-ttu-id="4f8d8-202">Sur la page **où voulez-vous enregistrer la demande hors connexion ?** , vous êtes invité à indiquer un **nom de fichier** et un **format de fichier** pour l’enregistrement de la demande de signature de certificat.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-202">On the **Where do you want to save the offline request?** page, you are prompted for a **File Name** and a **File Format** for saving the certificate signing request.</span></span>

18. <span data-ttu-id="4f8d8-203">Dans le champ **nom de fichier** , tapez le chemin d’accès et le nom de fichier de la demande, ou cliquez sur **Parcourir** pour sélectionner un emplacement pour le fichier et tapez le nom de fichier de la demande.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-203">In the **File Name** entry field, type a path and filename for the request, or click **Browse** to select a location for the file and type the filename for the request.</span></span>

19. <span data-ttu-id="4f8d8-204">Pour **format de fichier**, cliquez sur **base 64** ou **binaire**.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-204">For **File format**, click either **Base 64** or **Binary**.</span></span> <span data-ttu-id="4f8d8-205">Sélectionnez **Base 64** , sauf si vous y êtes invité autrement par le fournisseur pour vos certificats.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-205">Select **Base 64** unless you are instructed otherwise by the vendor for your certificates.</span></span>

20. <span data-ttu-id="4f8d8-206">Recherchez le fichier de demande que vous avez enregistré à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-206">Locate the request file that you saved in the previous step.</span></span> <span data-ttu-id="4f8d8-207">Envoyez-le à votre autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-207">Submit to your public certification authority.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="4f8d8-208">Microsoft a identifié des autorités de certification publiques qui répondent aux exigences des communications unifiées.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-208">Microsoft has identified Public CAs that meets the requirements for Unified Communications purposes.</span></span> <span data-ttu-id="4f8d8-209">Une liste est conservée dans l’article suivant de la base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-209">A list is maintained in the following knowledge base article.</span></span> <A href="https://go.microsoft.com/fwlink/?linkid=282625">https://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

