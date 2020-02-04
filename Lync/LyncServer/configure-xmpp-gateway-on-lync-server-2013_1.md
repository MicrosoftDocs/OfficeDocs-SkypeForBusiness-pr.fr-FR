---
title: Configurer la passerelle XMPP sur Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: 00777a34-cc36-4992-9459-08c14543ef6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687953(v=OCS.15)
ms:contentKeyID: 49733538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82c7cec94a65a35f4f5141950c4691fec0b28706
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="d63cc-102">Configurer la passerelle XMPP sur Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d63cc-102">Configure XMPP gateway on Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d63cc-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="d63cc-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="d63cc-104">Lorsque vous configurez des stratégies pour la prise en charge des partenaires fédérés du protocole de messagerie extensible et de présence, les stratégies s’appliquent aux utilisateurs des domaines fédérés de XMPP, mais pas aux utilisateurs de services de messagerie instantanée SIP (Session Initiation Protocol). (par exemple, Windows Live) ou domaines fédérés SIP.</span><span class="sxs-lookup"><span data-stu-id="d63cc-104">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="d63cc-105">Vous configurez un partenaire fédéré de XMPP pour chaque domaine fédéré XMPP que vous voulez autoriser vos utilisateurs à ajouter des contacts et à communiquer avec eux.</span><span class="sxs-lookup"><span data-stu-id="d63cc-105">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="d63cc-106">Une fois les stratégies en place, des tâches supplémentaires incluent la configuration des certificats de passerelle XMPP, le déploiement de la passerelle de Lync Server 2013 XMPP et la mise à jour des enregistrements DNS pour la passerelle XMPP.</span><span class="sxs-lookup"><span data-stu-id="d63cc-106">Once the policies are in place, additional tasks include configuring the XMPP Gateway certificates, deploying the Lync Server 2013 XMPP Gateway, and finally updating the DNS records for the XMPP Gateway.</span></span>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="d63cc-107">Configurer des certificats de passerelle XMPP sur le serveur Edge Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d63cc-107">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="d63cc-108">Sur le serveur Edge, dans l’Assistant Déploiement, en regard de l' **étape 3 : demandez, installez ou attribuez des certificats**, cliquez de **nouveau sur exécuter**.</span><span class="sxs-lookup"><span data-stu-id="d63cc-108">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="d63cc-109">Si vous déployez le serveur Edge pour la première fois, vous verrez exécuter au lieu de réexécuter.</span><span class="sxs-lookup"><span data-stu-id="d63cc-109">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="d63cc-110">Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Créer une demande de certificat**.</span><span class="sxs-lookup"><span data-stu-id="d63cc-110">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="d63cc-111">Dans la page **demande de certificat** , cliquez sur certificat de **bord externe**.</span><span class="sxs-lookup"><span data-stu-id="d63cc-111">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="d63cc-112">Dans la page de **demande retardée ou immédiate** , activez la case à cocher **préparer la demande maintenant, puis l’envoyer plus tard** .</span><span class="sxs-lookup"><span data-stu-id="d63cc-112">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="d63cc-113">Dans la **page fichier de demande de certificat** , tapez le chemin d’accès complet et le nom du fichier dans lequel la demande doit être enregistrée (par exemple,\\c\_:\_CERT l’Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="d63cc-113">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="d63cc-114">Dans la page **spécifier un modèle de certificat secondaire** , pour utiliser un modèle autre que le modèle par défaut du serveur Web, activez la case à cocher utiliser un autre **modèle de certificat pour l’autorité de certification sélectionnée** .</span><span class="sxs-lookup"><span data-stu-id="d63cc-114">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="d63cc-115">Dans la page **paramètres de nom et de sécurité** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d63cc-115">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="d63cc-116">Dans **nom convivial**, tapez un nom d’affichage pour le certificat.</span><span class="sxs-lookup"><span data-stu-id="d63cc-116">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="d63cc-117">En **longueur**, spécifiez la longueur en bits (en général, la valeur par défaut 2048).</span><span class="sxs-lookup"><span data-stu-id="d63cc-117">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="d63cc-118">Vérifiez que la case à cocher **marquer le certificat en tant que clé publique en tant qu’export** est activée.</span><span class="sxs-lookup"><span data-stu-id="d63cc-118">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="d63cc-119">Dans la page informations sur l' **organisation** , tapez le nom de l’organisation et l’unité d’organisation (par exemple, une division ou un service).</span><span class="sxs-lookup"><span data-stu-id="d63cc-119">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="d63cc-120">Dans la page **informations géographiques** , spécifiez les informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="d63cc-120">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="d63cc-121">Sur la page nom de l’objet **/nom** de l’objet, les informations à remplir automatiquement par l’Assistant sont affichées.</span><span class="sxs-lookup"><span data-stu-id="d63cc-121">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="d63cc-122">Si d’autres noms d’objet sont nécessaires, vous pouvez les spécifier au cours des deux étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="d63cc-122">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="d63cc-123">Dans la page Configuration du protocole **SIP sur le nom de l’objet** , activez la case à cocher Domain pour ajouter un SIP. \<entrée\> sipdomain dans la liste noms de remplacement de l’objet.</span><span class="sxs-lookup"><span data-stu-id="d63cc-123">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="d63cc-124">Dans la page **configurez** d’autres noms d’objet, spécifiez d’autres noms d’objet obligatoires.</span><span class="sxs-lookup"><span data-stu-id="d63cc-124">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="d63cc-125">Si le proxy XMPP est installé, le nom de domaine par défaut (par exemple, contoso.com) est renseigné dans les entrées du SAN.</span><span class="sxs-lookup"><span data-stu-id="d63cc-125">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="d63cc-126">Si vous avez besoin d’entrées supplémentaires, ajoutez-les à cette étape.</span><span class="sxs-lookup"><span data-stu-id="d63cc-126">If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="d63cc-127">Dans la page Résumé de la **demande** , passez en revue les informations de certificat à utiliser pour générer la requête.</span><span class="sxs-lookup"><span data-stu-id="d63cc-127">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="d63cc-128">À la fin de l’exécution des commandes, vous pouvez **consulter le journal**ou cliquer sur **suivant** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="d63cc-128">After the commands finish running, you can **View Log**, or click **Next** to continue.</span></span>

15. <span data-ttu-id="d63cc-129">Dans la page **fichier de demande de certificat** , vous pouvez afficher le fichier de demande de signature de certificat généré (CSR) en cliquant sur Afficher ou quitter l’Assistant Certificat en cliquant sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="d63cc-129">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="d63cc-130">Copiez le fichier de demande et envoyez-le à votre autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="d63cc-130">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="d63cc-131">Après avoir reçu, importé et attribué le certificat public, vous devez arrêter et redémarrer les services Edge Server.</span><span class="sxs-lookup"><span data-stu-id="d63cc-131">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="d63cc-132">Pour cela, entrez dans la console de gestion de Lync Server :</span><span class="sxs-lookup"><span data-stu-id="d63cc-132">You do this by typing in the Lync Server Management console:</span></span>
    
       ```console
        Stop-CsWindowsService
       ```
    
       ```console
        Start-CsWindowsService
       ```

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="d63cc-133">Configurer une nouvelle passerelle XMPP Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d63cc-133">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="d63cc-134">Ouvrez le Paneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d63cc-134">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="d63cc-135">Dans la barre de navigation gauche, cliquez sur **Fédération et accès externe** , puis sur **partenaires fédérés de XMPP**.</span><span class="sxs-lookup"><span data-stu-id="d63cc-135">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="d63cc-136">Pour créer une nouvelle configuration, cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d63cc-136">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="d63cc-137">Définissez les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="d63cc-137">Define the following settings:</span></span>

5.  <span data-ttu-id="d63cc-138">**Domaine principal (**     obligatoire).</span><span class="sxs-lookup"><span data-stu-id="d63cc-138">**Primary domain**    (Required).</span></span> <span data-ttu-id="d63cc-139">Le domaine principal est le domaine de base du partenaire XMPP.</span><span class="sxs-lookup"><span data-stu-id="d63cc-139">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="d63cc-140">Par exemple, vous devez entrer **fabrikam.com** pour le nom de domaine de partenaire XMPP.</span><span class="sxs-lookup"><span data-stu-id="d63cc-140">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="d63cc-141">Il s’agit d’une entrée obligatoire.</span><span class="sxs-lookup"><span data-stu-id="d63cc-141">This is a required entry.</span></span>

6.  <span data-ttu-id="d63cc-142">**Description**   la description correspond aux notes ou autres informations d’identification pour cette configuration particulière.</span><span class="sxs-lookup"><span data-stu-id="d63cc-142">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="d63cc-143">Cette entrée est facultative.</span><span class="sxs-lookup"><span data-stu-id="d63cc-143">This entry is optional.</span></span>

7.  <span data-ttu-id="d63cc-144">**Domaines supplémentaires les**   domaines supplémentaires sont des domaines qui font partie du domaine de votre partenaire XMPP qui doivent être inclus dans le cadre de la communication XMPP autorisée.</span><span class="sxs-lookup"><span data-stu-id="d63cc-144">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="d63cc-145">Par exemple, si le domaine principal est **fabrikam.com**, vous répertoriez tous les autres domaines sous fabrikam.com que vous communiquerez par le biais de la fonction XMPP.</span><span class="sxs-lookup"><span data-stu-id="d63cc-145">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="d63cc-146">**Type**   de partenaire **le paramètre** est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="d63cc-146">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="d63cc-147">Vous devez choisir l’une des options suivantes pour décrire et mettre en œuvre les contacts qui peuvent être ajoutés.</span><span class="sxs-lookup"><span data-stu-id="d63cc-147">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="d63cc-148">Vous pouvez sélectionner l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d63cc-148">You can select from:</span></span>
    
      - <span data-ttu-id="d63cc-149">**Fédéré** Un type de partenaire **fédéré** représente un niveau élevé de confiance entre le déploiement de Lync Server et le partenaire XMPP.</span><span class="sxs-lookup"><span data-stu-id="d63cc-149">**Federated** A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="d63cc-150">Ce type de partenariat est recommandé pour la Fédération avec des serveurs XMPP au sein de la même entreprise ou pour lesquels une relation professionnelle est établie.</span><span class="sxs-lookup"><span data-stu-id="d63cc-150">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="d63cc-151">Les contacts XMPP dans les partenaires fédérés peuvent :</span><span class="sxs-lookup"><span data-stu-id="d63cc-151">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="d63cc-152">Ajoutez des contacts Lync et consultez leur statut de présence sans autorisation expresse de l’utilisateur Lync.</span><span class="sxs-lookup"><span data-stu-id="d63cc-152">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="d63cc-153">Envoyez des messages instantanés à vos contacts Lync, que l’utilisateur de Lync les a ajoutés à leur liste de contacts ou non.</span><span class="sxs-lookup"><span data-stu-id="d63cc-153">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="d63cc-154">Afficher les notes de statut d’un utilisateur Lync.</span><span class="sxs-lookup"><span data-stu-id="d63cc-154">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="d63cc-155">**Vérification publique le** fournisseur **certifié public** est un fournisseur XMPP public qui est approuvé pour vérifier l’identité de ses utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d63cc-155">**Public verified** A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="d63cc-156">Les contacts XMPP dans les réseaux validés publics peuvent ajouter des contacts Lync et afficher leur présence et leur envoyer des messages instantanés sans autorisation expresse des utilisateurs Lync.</span><span class="sxs-lookup"><span data-stu-id="d63cc-156">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="d63cc-157">Les contacts XMPP dans les réseaux validés publique ne voient jamais les notes d’état des utilisateurs Lync.</span><span class="sxs-lookup"><span data-stu-id="d63cc-157">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="d63cc-158">Ce paramètre n’est pas recommandé.</span><span class="sxs-lookup"><span data-stu-id="d63cc-158">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="d63cc-159">**Public non vérifié** Un partenaire non **vérifié public** est un fournisseur XMPP public qui n’est pas approuvé pour vérifier l’identité de ses utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d63cc-159">**Public unverified** A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="d63cc-160">Les utilisateurs de XMPP sur des réseaux publics non vérifiés ne peuvent pas communiquer avec des utilisateurs de Lync, sauf si l’utilisateur de Lync les a expressément autorisés en les ajoutant à la liste des contacts.</span><span class="sxs-lookup"><span data-stu-id="d63cc-160">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="d63cc-161">Les utilisateurs de XMPP sur les réseaux publics non vérifiés ne voient jamais les notes d’état des utilisateurs Lync.</span><span class="sxs-lookup"><span data-stu-id="d63cc-161">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="d63cc-162">Ce paramètre est recommandé pour toutes les fédérations avec les fournisseurs XMPP publics tels que Google Talk.</span><span class="sxs-lookup"><span data-stu-id="d63cc-162">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="d63cc-163">**Type de connexion :** Définit les différentes règles et paramètres de dialback.</span><span class="sxs-lookup"><span data-stu-id="d63cc-163">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="d63cc-164">**La négociation**   TLS définit les règles de négociation TLS.</span><span class="sxs-lookup"><span data-stu-id="d63cc-164">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="d63cc-165">Un service XMPP peut nécessiter le protocole TLS, peut rendre TLS facultatif ou vous définissez que TLS n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="d63cc-165">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="d63cc-166">Le choix de l’option facultative quitte le service XMPP pour une décision de demande obligatoire.</span><span class="sxs-lookup"><span data-stu-id="d63cc-166">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="d63cc-167">Pour afficher tous les paramètres et détails possibles relatifs aux négociations SASL, TLS et Dialback, y compris les configurations d’erreur non valides et connues, voir [paramètres de négociation des partenaires fédérés de XMPP dans Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span><span class="sxs-lookup"><span data-stu-id="d63cc-167">To view all possible settings and details for SASL, TLS and Dialback negotiation – including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span></span>
        
           - <span data-ttu-id="d63cc-168">**Requis**   le service XMPP nécessite une négociation TLS.</span><span class="sxs-lookup"><span data-stu-id="d63cc-168">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
           - <span data-ttu-id="d63cc-169">**Facultatif**   le service XMPP indique que le protocole TLS est requis pour négocier.</span><span class="sxs-lookup"><span data-stu-id="d63cc-169">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="d63cc-170">**Non pris en charge**   le service XMPP ne prend pas en charge le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="d63cc-170">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="d63cc-171">**La négociation**   SASL définit les règles de négociation SASL.</span><span class="sxs-lookup"><span data-stu-id="d63cc-171">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="d63cc-172">Un service XMPP peut être requis pour rendre SASL une option de SASL, ou vous définissez que SASL n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="d63cc-172">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="d63cc-173">Le choix facultatif pour une décision d’obligation de négociation est requis par le service XMPP du partenaire.</span><span class="sxs-lookup"><span data-stu-id="d63cc-173">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
           - <span data-ttu-id="d63cc-174">**Requis**   le service XMPP nécessite une négociation SASL.</span><span class="sxs-lookup"><span data-stu-id="d63cc-174">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
           - <span data-ttu-id="d63cc-175">**Facultatif**   le service XMPP indique que SASL est requis pour négocier.</span><span class="sxs-lookup"><span data-stu-id="d63cc-175">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="d63cc-176">**Non pris en charge**   le service XMPP ne prend pas en charge SASL.</span><span class="sxs-lookup"><span data-stu-id="d63cc-176">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="d63cc-177">**Service de support dialback Negotiation** Le processus de négociation du serveur de support dialback utilise le DNS (Domain Name System) et un serveur faisant autorité pour vérifier que la requête provient d’un partenaire XMPP valide.</span><span class="sxs-lookup"><span data-stu-id="d63cc-177">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="d63cc-178">Pour ce faire, le serveur d’origine crée un message d’un type spécifique avec une clé dialback générée et recherche le serveur de réception dans DNS.</span><span class="sxs-lookup"><span data-stu-id="d63cc-178">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="d63cc-179">Le serveur d’origine envoie la clé dans un flux XML à la recherche DNS résultante, le serveur de réception en principe.</span><span class="sxs-lookup"><span data-stu-id="d63cc-179">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="d63cc-180">Dès réception de la clé via le flux XML, le serveur de réception ne répond pas au serveur d’origine, mais envoie la clé à un serveur faisant autorité connu.</span><span class="sxs-lookup"><span data-stu-id="d63cc-180">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="d63cc-181">Le serveur faisant autorité vérifie que la clé est valide ou n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="d63cc-181">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="d63cc-182">Si ce n’est pas le cas, le serveur de réception ne répond pas au serveur d’origine.</span><span class="sxs-lookup"><span data-stu-id="d63cc-182">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="d63cc-183">Si la clé est valide, le serveur de réception informe le serveur d’origine qu’elle est valide et qu’elle peut commencer.</span><span class="sxs-lookup"><span data-stu-id="d63cc-183">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="d63cc-184">Il existe deux États valides pour la **négociation Dialback**:</span><span class="sxs-lookup"><span data-stu-id="d63cc-184">There are two valid states for **Dialback negotiation**:</span></span>
        
           - <span data-ttu-id="d63cc-185">**True**   le serveur XMPP est configuré pour utiliser la négociation Dialback si une requête doit être reçue d’un serveur d’origine.</span><span class="sxs-lookup"><span data-stu-id="d63cc-185">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
           - <span data-ttu-id="d63cc-186">**False**   : le serveur XMPP n’est pas configuré pour utiliser la négociation Dialback et si une requête doit être reçue d’un serveur d’origine, il est ignoré.</span><span class="sxs-lookup"><span data-stu-id="d63cc-186">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="d63cc-187">Cliquez sur **valider** pour enregistrer les modifications apportées à la stratégie de site ou d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d63cc-187">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="d63cc-188">Mettre à jour les enregistrements DNS pour Lync Server 2013 passerelle XMPP</span><span class="sxs-lookup"><span data-stu-id="d63cc-188">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="d63cc-189">Pour configurer DNS pour la Fédération XMPP, ajoutez l’enregistrement SRV suivant à votre DNS externe :\_XMPP-Server. \_TCP. \<nom de\> domaine l’enregistrement SRV sera résolu vers le nom de domaine complet d’accès du serveur Edge, avec une valeur de port de 5269.</span><span class="sxs-lookup"><span data-stu-id="d63cc-189">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

