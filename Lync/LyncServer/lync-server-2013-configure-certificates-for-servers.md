---
title: 'Lync Server 2013 : configuration des certificats pour les serveurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e2fd3ce8c229fad2f990d5f295e4c4454ef153e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a><span data-ttu-id="83431-102">Configurer des certificats pour les serveurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83431-102">Configure certificates for servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83431-103">_**Dernière modification de la rubrique :** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="83431-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="83431-104">Pour effectuer cette procédure, vous devez avoir ouvert une session en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins ou disposer des autorisations déléguées correctes.</span><span class="sxs-lookup"><span data-stu-id="83431-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="83431-105">Pour plus d’informations sur la délégation d’autorisations, consultez la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="83431-105">For details about delegating permissions, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="83431-106">En fonction de votre entreprise et des besoins en matière de certificats, il se peut que vous deviez appartenir à d’autres groupes.</span><span class="sxs-lookup"><span data-stu-id="83431-106">Depending on your organization and requirements for requesting certificates, you may require other group memberships.</span></span> <span data-ttu-id="83431-107">Contactez le groupe chargé de gérer l’autorité de certification de votre infrastructure de clés publiques.</span><span class="sxs-lookup"><span data-stu-id="83431-107">Consult with the group that manages your public key infrastructure (PKI) certification authority (CA).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83431-108">Lync Server 2013 inclut la prise en charge de la suite SHA-2 (SHA-2 utilise les longueurs de chiffrement de 224, 256, 384 ou 512 bits) des algorithmes de hachage et de signature Digest pour les connexions à partir de clients exécutant Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista ou Systèmes d’exploitation Windows XP, en plus de Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="83431-108">Lync Server 2013 includes support for the SHA-2 suite (SHA-2 uses digest lengths of 224, 256, 384 or 512 bits) of digest hash and signing algorithms for connections from clients running the Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista, or Windows XP operating systems, in addition to Lync Phone Edition.</span></span> <span data-ttu-id="83431-109">Pour prendre en charge l’accès externe à l’aide de la suite SHA-2, le certificat externe est émis par une autorité de certification publique qui peut également émettre un certificat avec le même chiffrement de longueur en bits.</span><span class="sxs-lookup"><span data-stu-id="83431-109">To support external access using the SHA-2 suite, the external certificate is issued by a public CA that also can issue a certificate with the same bit length digest.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="83431-110">La sélection de l’algorithme de hachage et du Digest de hachage dépend des clients et des serveurs qui utiliseront le certificat, ainsi que d’autres ordinateurs et appareils avec lesquels les clients et les serveurs communiqueront, qui doivent également savoir comment utiliser les algorithmes utilisés dans le titre.</span><span class="sxs-lookup"><span data-stu-id="83431-110">The selection of which hash digest and signing algorithm is dependent on the clients and the servers that will use the certificate, and other computers and devices that clients and servers will communicate with who must also know how to use the algorithms used in the certificate.</span></span> <span data-ttu-id="83431-111">Pour plus d’informations sur les longueurs de résumé prises en charge dans le système d’exploitation<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>et certaines applications clientes, reportez-vous à la rubrique.</span><span class="sxs-lookup"><span data-stu-id="83431-111">For information on which digest lengths are supported in the operating system and some client applications, see<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>.</span></span>



</div>

<span data-ttu-id="83431-112">Chaque serveur Standard Edition ou serveur frontal requiert jusqu’à quatre certificats : le certificat oAuthTokenIssuer, un certificat par défaut, un certificat interne Web et un certificat externe Web.</span><span class="sxs-lookup"><span data-stu-id="83431-112">Each Standard Edition server or Front End Server requires up to four certificates: the oAuthTokenIssuer certificate, a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="83431-113">Cependant, il est possible de demander et d’attribuer un certificat par défaut unique contenant les entrées de noms d’objet appropriées ainsi que le certificat de l’émetteur de jetons OAuth.</span><span class="sxs-lookup"><span data-stu-id="83431-113">However, it is possible to request and assign a single default certificate with appropriate subject alternative name entries as well as the oAuthTokenIssuer certificate.</span></span> <span data-ttu-id="83431-114">Pour plus d’informations sur les certificats requis, reportez-vous à [Certificate Requirements for Internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span><span class="sxs-lookup"><span data-stu-id="83431-114">For details about the certificate requirements, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span></span> <span data-ttu-id="83431-115">Pour plus d’informations sur la demande, l’affectation et l’installation du certificat oAuthTokenIssuer, reportez-vous à la rubrique [Managing Server-to-Server Authentication (OAuth) and Partner applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="83431-115">For details about requesting, assigning and installing the oAuthTokenIssuer certificate, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

<span data-ttu-id="83431-116">Utilisez la procédure suivante pour demander, attribuer et installer le serveur Standard Edition ou les certificats de serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="83431-116">Use the following procedure to request, assign, and install the Standard Edition server or Front End Server certificates.</span></span> <span data-ttu-id="83431-117">Répétez la procédure pour chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="83431-117">Repeat the procedure for each Front End Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="83431-118">La procédure suivante décrit la configuration des certificats à partir d’une infrastructure à clé publique (PKI) d’entreprise interne déployée par votre entreprise et avec un traitement hors ligne de la demande.</span><span class="sxs-lookup"><span data-stu-id="83431-118">The following procedure describes how to configure certificates from an internal enterprise PKI deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="83431-119">Pour plus d’informations sur l’obtention de certificats auprès d’une autorité de certification publique, voir <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Certificate Requirements for Internal servers in Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="83431-119">For information about obtaining certificates from a public CA, see <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Certificate requirements for internal servers in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="83431-120">Cette procédure décrit également comment demander, attribuer et installer des certificats lors de la configuration du serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="83431-120">Also, this procedure describes how to request, assign, and install certificates during set up of the Front End Server.</span></span> <span data-ttu-id="83431-121">Si vous avez demandé des certificats à l’avance, comme décrit dans la section <A href="lync-server-2013-request-certificates-in-advance-optional.md">demander des certificats à l’avance (facultatif) pour Lync Server 2013</A> de cette documentation de déploiement, ou si vous n’utilisez pas une PKI d’entreprise interne déployée dans votre organisation pour obtenir des certificats, vous devez modifier cette procédure selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="83431-121">If you requested certificates in advance, as described in the <A href="lync-server-2013-request-certificates-in-advance-optional.md">Request certificates in advance (optional) for Lync Server 2013</A> section of this Deployment documentation, or you do not use an internal enterprise PKI deployed in your organization to obtain certificates, you must modify this procedure as appropriate.</span></span>



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a><span data-ttu-id="83431-122">Pour configurer des certificats pour un serveur frontal</span><span class="sxs-lookup"><span data-stu-id="83431-122">To configure certificates for a Front End Server</span></span>

1.  <span data-ttu-id="83431-123">Dans l’Assistant Déploiement Lync Server, cliquez sur **exécuter** en regard de l' **étape 3 : demander, installer ou assigner des certificats**.</span><span class="sxs-lookup"><span data-stu-id="83431-123">In the Lync Server Deployment Wizard, click **Run** next to **Step 3: Request, Install or Assign Certificates**.</span></span>

2.  <span data-ttu-id="83431-124">Dans la page **Assistant Certificat**, cliquez sur **Demander**.</span><span class="sxs-lookup"><span data-stu-id="83431-124">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="83431-125">Dans la page **Demande de certificat**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="83431-125">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="83431-p107">Dans la page **Demandes différées ou immédiates**, vous pouvez accepter l’option par défaut **Envoyer la demande immédiatement à une autorité de certification en ligne** en cliquant sur **Suivant**. L’autorité de certification interne avec inscription en ligne automatique doit être disponible si vous sélectionnez cette option. Si vous choisissez de mettre la demande en attente, vous serez invité à indiquer un nom et un emplacement pour enregistrer le fichier de demande de certificat. La demande de certificat doit être présentée et traitée par une autorité de certification interne à votre entreprise ou publique. Vous devrez ensuite importer la réponse du certificat et lui attribuer le rôle approprié.</span><span class="sxs-lookup"><span data-stu-id="83431-p107">On the **Delayed or Immediate Requests** page, you can accept the default **Send the request immediately to an online certification authority** option by clicking **Next**. The internal CA with automatic online enrollment must be available if you select this option. If you choose the option to delay the request, you will be prompted for a name and location to save the certificate request file. The certificate request must be presented and processed by a CA either inside your organization, or by a public CA. You will then need to import the certificate response and assign it to the proper certificate role.</span></span>

5.  <span data-ttu-id="83431-131">Sur la page **choisir une autorité** de certification, sélectionnez l’option **Sélectionner une autorité de certification dans la liste détectée dans votre environnement** , puis sélectionnez une autorité de certification connue (par le biais de l’inscription dans les services de domaine Active Directory) dans la liste.</span><span class="sxs-lookup"><span data-stu-id="83431-131">On the **Choose a Certificate Authority (CA)** page, select the **Select a CA from the list detected in your environment** option, and then select a known (through registration in Active Directory Domain Services) CA from the list.</span></span> <span data-ttu-id="83431-132">Ou sélectionnez l’option **Spécifier une autre autorité de certification**, entrez le nom d’une autre autorité de certification dans la zone, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="83431-132">Or, select the **Specify another certification authority** option, enter the name of another CA in the box, and then click **Next**.</span></span>

6.  <span data-ttu-id="83431-p109">Sur la page **Compte d’autorité de certification**, vous êtes invité à saisir des informations d’identification pour demander et traiter la demande de certificat auprès de l’autorité de certification. Vous devez avoir déterminé si un nom d’utilisateur et un mot de passe sont nécessaires pour demander un certificat à l’avance. Votre administrateur de l’autorité de certification dispose des informations requises et peut vous assister pour cette étape. Si vous devez fournir des informations d’identification de remplacement, saisissez un nom d’utilisateur et un mot de passe dans les champs de texte, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="83431-p109">On the **Certificate Authority Account** page, you are prompted for credentials to request and process the certificate request at the CA. You should have determined if a user name and password is necessary to request a certificate in advance. Your CA administrator will have the required information and may have to assist you in this step. If you need to supply alternate credentials, select the check box, provide a user name and password in the text boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="83431-137">Sur la page **Spécifier un autre modèle de certificat**, pour utiliser le modèle de serveur Web par défaut, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="83431-137">On the **Specify Alternate Certificate Template** page, to use the default Web Server template, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83431-p110">Si votre entreprise a créé un modèle à employer en remplacement du modèle d’autorité de certification de serveur web, activez la case à cocher et entrez le nom du modèle de remplacement. Vous devez utiliser le nom du modèle défini par l’administrateur de l’autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="83431-p110">If your organization has created a template for use as an alternative for the default Web server CA template, select the check box, and then enter the name of the alternate template. You will need the template name as defined by the CA administrator.</span></span>

    
    </div>

8.  <span data-ttu-id="83431-p111">Sur la page **Nom et paramètres de sécurité**, spécifiez un **Nom convivial** devant vous permettre d’identifier le certificat et son utilisation. Si vous laissez ce champ vide, un nom est créé automatiquement. Définissez la **Longueur en bits** de la clé, ou acceptez la valeur par défaut de 2 048 bits. Sélectionnez l’option **Marquer la clé privée du certificat comme exportable** si vous estimez que le certificat et la clé privée doivent être déplacés ou copiés sur d’autres systèmes, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="83431-p111">On the **Name and Security Settings** page, specify a **Friendly Name** that should allow you to identify the certificate and purpose. If you leave it blank, a name will be generated automatically. Set the **Bit length** of the key, or accept the default of 2048 bits. Select the **Mark the certificate’s private key as exportable** if you determine that the certificate and private key needs to be moved or copied to other systems, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83431-144">Lync Server 2013 a une configuration minimale requise pour une clé privée exportable.</span><span class="sxs-lookup"><span data-stu-id="83431-144">Lync Server 2013 has minimal requirements for an exportable private key.</span></span> <span data-ttu-id="83431-145">L’un de ces emplacements concerne les serveurs Edge dans un pool, où le service d’authentification du serveur relais multimédia utilise des copies du certificat au lieu de plusieurs certificats individuels pour chaque instance du pool.</span><span class="sxs-lookup"><span data-stu-id="83431-145">One such place is on the Edge Servers in a pool, where the Media Relay Authentication Service uses copies of the certificate, rather than individual certificates for each instance in the pool.</span></span>

    
    </div>

9.  <span data-ttu-id="83431-146">Dans la page **Informations relatives à l’entreprise**, entrez éventuellement des informations sur l’entreprise, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="83431-146">On the **Organization Information** page, optionally provide organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="83431-147">Dans la page **Informations géographiques**, entrez éventuellement des informations géographiques, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="83431-147">On the **Geographical Information** page, optionally provide geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="83431-148">Sur la page **Nom du sujet/Autres noms du sujet**, passez en revue les autres noms du sujet à ajouter, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="83431-148">On the **Subject Name / Subject Alternate Names** page, review the subject alternative names that will be added, and then click **Next**.</span></span>

12. <span data-ttu-id="83431-149">Dans la page **Paramètre du domaine SIP**, sélectionnez le **domaine SIP**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="83431-149">On the **SIP Domain setting** page, select the **SIP Domain**, and then click **Next**.</span></span>

13. <span data-ttu-id="83431-150">Dans la page **Configurer d’autres noms du sujet supplémentaires**, ajoutez d’éventuels noms de sujet supplémentaires requis, y compris ceux nécessaires aux futurs domaines SIP supplémentaires, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="83431-150">On the **Configure Additional Subject Alternate Names** page, add any additional required subject alternative names, including any that might be required for additional SIP domains in the future, and then click **Next**.</span></span>

14. <span data-ttu-id="83431-p113">Dans la page **Résumé de la demande de certificat**, passez en revue les informations du résumé. Si les informations sont correctes, cliquez sur **Suivant**. Si vous devez corriger ou modifier un paramètre, cliquez sur **Précédent** pour revenir à la page correspondante afin d’y apporter la correction ou modification requise.</span><span class="sxs-lookup"><span data-stu-id="83431-p113">On the **Certificate Request Summary** page, review the information in the summary. If the information is correct, click **Next**. If you need to correct or modify a setting, click **Back** to the proper page to make the correction or modification.</span></span>

15. <span data-ttu-id="83431-154">Dans la page **Exécution de commandes**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="83431-154">On the **Executing Commands** page, click **Next**.</span></span>

16. <span data-ttu-id="83431-155">Dans la page **État de la demande de certificat en ligne**, passez en revue les informations affichées.</span><span class="sxs-lookup"><span data-stu-id="83431-155">On the **Online Certificate Request Status** page, review the information returned.</span></span> <span data-ttu-id="83431-156">Notez que le certificat a été émis et installé dans le magasin de certificats local.</span><span class="sxs-lookup"><span data-stu-id="83431-156">You should note that the certificate was issued and installed into the local certificate store.</span></span> <span data-ttu-id="83431-157">Si elle est signalée comme ayant été émise et installée, mais n’est pas valide, vérifiez que le certificat racine de l’autorité de certification a été installé dans le magasin d’AC racines de confiance du serveur.</span><span class="sxs-lookup"><span data-stu-id="83431-157">If it is reported as having been issued and installed, but is not valid, make sure that the CA root certificate has been installed in the server’s Trusted Root CA store.</span></span> <span data-ttu-id="83431-158">Consultez la documentation de votre autorité de certification pour savoir comment extraire le certificat d’une autorité de certification racine de confiance.</span><span class="sxs-lookup"><span data-stu-id="83431-158">Refer to your CA documentation on how to retrieve a Trusted Root CA certificate.</span></span> <span data-ttu-id="83431-159">Si vous devez consulter le certificat extrait, cliquez sur **Afficher les détails du certificat**.</span><span class="sxs-lookup"><span data-stu-id="83431-159">If you need to view the retrieved certificate, click **View Certificate Details**.</span></span> <span data-ttu-id="83431-160">Par défaut, la case à cocher **Attribuer ce certificat aux utilisations de certificat Lync Server** est activée.</span><span class="sxs-lookup"><span data-stu-id="83431-160">By default, the check box for **Assign the certificate to Lync Server certificate usages** is checked.</span></span> <span data-ttu-id="83431-161">Si vous souhaitez attribuer manuellement le certificat, désactivez la case à cocher, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="83431-161">If you want to manually assign the certificate, clear the check box, and then click **Finish**.</span></span>

17. <span data-ttu-id="83431-p115">Si vous avez désactivé la case à cocher **Attribuer ce certificat aux utilisations de certificat Lync Server** dans la page précédente, la page **Attribution de certificat** apparaît. Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="83431-p115">If you cleared the check box for **Assign the certificate to Lync Server certificate usages** on the previous page, you will be presented with the **Certificate Assignment** page. Click **Next**.</span></span>

18. <span data-ttu-id="83431-p116">Dans la page **Magasin de certificats**, sélectionnez le certificat que vous avez demandé. Si vous souhaitez afficher le certificat, cliquez sur **Afficher les détails du certificat**, puis sur **Suivant** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="83431-p116">On the **Certificate Store** page, select the certificate that you requested. If you want to view the certificate, click **View Certificate Details**, and then click **Next** to continue.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83431-p117">Si la page <STRONG>État de la demande de certificat en ligne</STRONG> a signalé un problème de certificat, par exemple que le certificat n’est pas valide, l’affichage du certificat réel peut vous aider à résoudre ce problème. Il existe deux problèmes spécifiques pouvant entraîner l’invalidité d’un certificat : il manque le certificat de l’autorité de certification racine de confiance indiqué ci-dessus et il manque une clé privée associée au certificat. Consultez la documentation de votre autorité de certification pour résoudre ces deux problèmes.</span><span class="sxs-lookup"><span data-stu-id="83431-p117">If the <STRONG>Online Certificate Request Status</STRONG> page reported an issue with the certificate, such as the certificate not being valid, viewing the actual certificate can assist in resolving the issue. Two specific issues that can cause a certificate to not be valid is the previously mentioned missing Trusted Root CA certificate, and a missing private key that is associated with the certificate. Refer to your CA documentation to resolve these two issues.</span></span>

    
    </div>

19. <span data-ttu-id="83431-169">Sur la page Résumé de l' **affectation du certificat** , passez en revue les informations présentées pour vérifier qu’il s’agit bien du certificat à attribuer, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="83431-169">On the **Certificate Assignment Summary** page, review the information presented to make sure that this is the certificate that should be assigned, and then click **Next**.</span></span>

20. <span data-ttu-id="83431-p118">Dans la page **Exécution de commandes**, passez en revue le résultat de la commande. Cliquez sur **Afficher le journal** si vous souhaitez passer en revue le processus d’attribution ou en cas d’erreur ou d’avertissement. Lorsque vous avez terminé votre vérification, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="83431-p118">On the **Executing Commands** page, review the output of the command. Click **View Log** if you want to review the assignment process or if there was an error or warning issued. When you are finished with your review, click **Finish**.</span></span>

21. <span data-ttu-id="83431-173">Dans la page **Assistant Certificat**, vérifiez que l’option **État** du certificat affiche « Attribué », puis cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="83431-173">On the **Certificate Wizard** page, verify that the **Status** of the certificate is “Assigned,” and then click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="83431-174">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="83431-174">See Also</span></span>


[<span data-ttu-id="83431-175">Configuration requise pour l’infrastructure de certificat pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83431-175">Certificate infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

