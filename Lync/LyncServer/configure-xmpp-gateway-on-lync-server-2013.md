---
title: Configuration de la passerelle XMPP sur Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: c70282e0-b502-47e2-a0be-a32eb1faf99d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721881(v=OCS.15)
ms:contentKeyID: 49733816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30dc21ddbbfd5d65d6834ffa5a6181c5e4a13b1c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503181"
---
# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="7d8e8-102">Configuration de la passerelle XMPP sur Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d8e8-102">Configure XMPP gateway on Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d8e8-103">_**Dernière modification de la rubrique :** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="7d8e8-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="7d8e8-104">Les dernières étapes de la migration de votre passerelle XMPP sont la configuration des certificats pour le serveur Edge Lync Server 2013, le déploiement de la passerelle XMPP Lync Server 2013 et la mise à jour des enregistrements DNS pour la passerelle XMPP.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-104">The final steps for migrating your XMPP Gateway are to configure certificates for the Lync Server 2013 Edge Server, deploy the Lync Server 2013 XMPP Gateway, and update the DNS records for the XMPP Gateway.</span></span> <span data-ttu-id="7d8e8-105">Ces étapes doivent être effectuées en parallèle pour réduire le temps d’arrêt de votre passerelle XMPP.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-105">These steps should be performed in parallel to minimize the down time of your XMPP Gateway.</span></span> <span data-ttu-id="7d8e8-106">Tous les utilisateurs doivent être déplacés vers votre déploiement Microsoft Lync Server 2013 avant d’effectuer ces étapes.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-106">All users must be moved to your Microsoft Lync Server 2013 deployment before performing these steps.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="7d8e8-107">La Fédération XMPP n’est pas prise en charge pour les utilisateurs hébergés sur les Survivable Branch Appliances.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-107">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="7d8e8-108">Cela s’applique à la fois aux informations de présence et à l’échange de messages INSTANTANÉs.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-108">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="7d8e8-109">Configurer des certificats pour la passerelle XMPP sur le serveur Edge Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d8e8-109">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="7d8e8-110">Sur le serveur Edge, dans l’Assistant Déploiement, à côté d’**Étape 3 : Demander, installer ou assigner les certificats**, cliquez sur **Réexécuter**.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-110">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="7d8e8-111">Si vous déployez pour la première fois le serveur Edge, l’option Exécuter s’affiche au lieu de Réexécuter.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-111">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="7d8e8-112">Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Créer une demande de certificat**.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-112">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="7d8e8-113">Dans la page **Demande de certificat**, cliquez sur **Certificat de serveur Edge externe**.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-113">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="7d8e8-114">Dans la page **Demande différée ou immédiate**, cochez la case **Préparer la demande maintenant, mais l’envoyer plus tard**.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-114">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="7d8e8-115">Dans la page **fichier de demande de certificat** , tapez le chemin d’accès complet et le nom du fichier dans lequel la demande doit être enregistrée (par exemple, c : \\ CERT \_ exernal \_ Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="7d8e8-115">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="7d8e8-116">Dans la page **Spécifier un autre modèle de certificat**, pour utiliser un autre modèle que le modèle WebServer par défaut, cochez la case **Utiliser un autre modèle de certificat pour l’autorité de certification sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-116">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="7d8e8-117">Dans la page **Nom et paramètres de sécurité**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="7d8e8-117">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="7d8e8-118">Dans **Nom convivial**, tapez un nom d’affichage du certificat.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-118">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="7d8e8-119">Dans **Longueur en bits**, spécifiez la longueur en bits (la valeur par défaut est 2048).</span><span class="sxs-lookup"><span data-stu-id="7d8e8-119">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="7d8e8-120">Vérifiez que la case **Marquer la clé privée du certificat comme exportable** est cochée.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-120">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="7d8e8-121">Dans la page **Informations relatives à l’organisation**, tapez le nom de l’organisation et de l’unité d’organisation (par exemple, une division ou un service).</span><span class="sxs-lookup"><span data-stu-id="7d8e8-121">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="7d8e8-122">Dans la page **Informations géographiques**, spécifiez les informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-122">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="7d8e8-p103">Dans la page **Nom du sujet/Autres noms du sujet**, le système affiche les informations automatiquement renseignées par l’Assistant. Si d’autres noms du sujet doivent être ajoutés, spécifiez-les dans les deux étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-p103">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="7d8e8-125">Sur la page **paramètre du domaine SIP sur les autres noms du sujet** , activez la case à cocher domaine pour ajouter un SIP.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="7d8e8-125">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\></span></span> <span data-ttu-id="7d8e8-126">entrée de la liste des autres noms du sujet.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-126">entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="7d8e8-127">Dans la page **Configurer d’autres noms du sujet supplémentaires** , spécifiez les autres noms du sujet supplémentaires nécessaires.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-127">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="7d8e8-p105">Si le proxy XMPP est installé, le nom de domaine par défaut (par exemple, contoso.com) est mentionné dans les entrées du SAN. Si vous nécessitez d’autres entrées, ajoutez-les pendant cette étape.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-p105">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="7d8e8-130">Dans la page **Résumé de la demande**, vérifiez les informations de certificat à utiliser pour générer la demande.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-130">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="7d8e8-131">Une fois les commandes entièrement exécutées, vous pouvez **Afficher le journal** ou cliquer sur Suivant pour continuer.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-131">After the commands finish running, you can **View Log**, or click Next to continue.</span></span>

15. <span data-ttu-id="7d8e8-132">Dans la page \*\*Fichier de demande de certificat \*\*, vous pouvez afficher le fichier de demande de signature de certificat (CSR) généré en cliquant sur \*\*Afficher \*\* ou quitter l’Assistant Certificat en cliquant sur \*\*Terminer \*\*.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-132">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking **View** or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="7d8e8-133">Copiez le fichier de la demande et transmettez-le à votre autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-133">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="7d8e8-p106">Après la réception, l’importation et l’affectation du certificat public, vous devez redémarrer les services du serveur Edge. Pour cela, tapez dans la console de gestion Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-p106">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="7d8e8-136">Configurer une nouvelle passerelle XMPP Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d8e8-136">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="7d8e8-137">Ouvrez le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-137">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="7d8e8-138">Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Partenaires fédérés XMPP**.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-138">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="7d8e8-139">Pour créer une configuration, cliquez sur **Nouvelle**.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-139">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="7d8e8-140">Définissez les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="7d8e8-140">Define the following settings:</span></span>

5.  <span data-ttu-id="7d8e8-141">**Domaine principal**     (Obligatoire).</span><span class="sxs-lookup"><span data-stu-id="7d8e8-141">**Primary domain**    (Required).</span></span> <span data-ttu-id="7d8e8-142">Le domaine principal correspond au domaine de base du partenaire XMPP.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-142">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="7d8e8-143">Par exemple, vous pouvez entrer **fabrikam.com** comme nom de domaine du partenaire XMPP.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-143">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="7d8e8-144">Cette entrée est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-144">This is a required entry.</span></span>

6.  <span data-ttu-id="7d8e8-145">**Description**     La description est destinée aux notes ou à d’autres informations d’identification pour cette configuration particulière.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-145">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="7d8e8-146">Cette entrée est facultative.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-146">This entry is optional.</span></span>

7.  <span data-ttu-id="7d8e8-147">**Domaines supplémentaires**     Les domaines supplémentaires sont des domaines qui font partie du domaine de votre partenaire XMPP qui doivent être inclus dans le cadre de la communication XMPP autorisée.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-147">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="7d8e8-148">Par exemple, si le domaine principal est **fabrikam.com**, vous devez répertorier tous les autres domaines sous fabrikam.com que vous communiquez avec par le biais de XMPP.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-148">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="7d8e8-149">**Type**     de partenaire Le **type de partenaire** est un paramètre obligatoire.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-149">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="7d8e8-150">Vous devez choisir l’une des options suivantes pour décrire et appliquer les contacts pouvant être ajoutés.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-150">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="7d8e8-151">Vous pouvez sélectionner l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="7d8e8-151">You can select from:</span></span>
    
      - <span data-ttu-id="7d8e8-152">**Fédéré**     Un type de partenaire **fédéré** représente un niveau élevé de confiance entre le déploiement Lync Server et le partenaire XMPP.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-152">**Federated**   A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="7d8e8-153">Ce type de partenaire est recommandé pour la fédération avec des serveurs XMPP dans la même entreprise ou si une relation entre entreprises est établie.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-153">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="7d8e8-154">Les contacts XMPP au sein des partenaires fédérés peuvent :</span><span class="sxs-lookup"><span data-stu-id="7d8e8-154">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="7d8e8-155">ajouter des contacts Lync et afficher leur présence sans autorisation explicite de l’utilisateur de Lync ;</span><span class="sxs-lookup"><span data-stu-id="7d8e8-155">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="7d8e8-156">envoyer des messages instantanés aux contacts Lync, que l’utilisateur de Lync les ait ajoutés à leur liste des contacts ou non ;</span><span class="sxs-lookup"><span data-stu-id="7d8e8-156">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="7d8e8-157">afficher les notes de statut de l’utilisateur de Lync.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-157">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="7d8e8-158">**Public vérifié**     Un partenaire de service **public vérifié** est un fournisseur XMPP public approuvé pour vérifier l’identité de ses utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-158">**Public verified**   A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="7d8e8-159">Les contacts XMPP dans les réseaux Public vérifié peuvent ajouter des contacts Lync, afficher la présence de ces derniers et leur envoyer des messages instantanés sans autorisation explicite des utilisateurs de Lync.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-159">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="7d8e8-160">Les contacts XMPP dans les réseaux Public vérifié ne peuvent jamais afficher les notes de statut des utilisateurs de Lync.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-160">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="7d8e8-161">Ce paramètre n’est pas recommandé.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-161">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="7d8e8-162">**Public non vérifié**     Un partenaire non **vérifié public** est un fournisseur XMPP public qui n’est pas approuvé pour vérifier l’identité de ses utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-162">**Public unverified**   A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="7d8e8-163">Les utilisateurs XMPP dans les réseaux Public non vérifié ne peuvent pas communiquer avec les utilisateurs de Lync sauf si l’utilisateur de Lync les a autorisés de façon explicite à les ajouter à la liste des contacts.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-163">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="7d8e8-164">Les utilisateurs XMPP dans les réseaux Public vérifié ne peuvent jamais afficher les notes de statut des utilisateurs de Lync.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-164">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="7d8e8-165">Ce paramètre est recommandé pour toutes les fédérations avec des fournisseurs XMPP publics comme Google Talk.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-165">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="7d8e8-166">**Type de connexion :** définit les différentes règles et paramètres de rappel.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-166">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="7d8e8-167">**Négociation TLS**     Définit les règles de négociation TLS.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-167">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="7d8e8-168">Un service XMPP peut nécessiter TLS, peut rendre TLS facultatif ou vous pouvez décider de ne pas prendre en charge TLS.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-168">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="7d8e8-169">Si vous choisissez Facultatif, le service XMPP est responsable de la décision sur la négociation obligatoire.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-169">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="7d8e8-170">Pour afficher tous les paramètres et détails possibles pour la négociation SASL, TLS et rappel, y compris les configurations d’erreur connues et non valides-voir [paramètres de négociation pour les partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span><span class="sxs-lookup"><span data-stu-id="7d8e8-170">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="7d8e8-171">**Obligatoire**     Le service XMPP nécessite la négociation TLS.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-171">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="7d8e8-172">**Facultatif**     Le service XMPP indique que TLS est obligatoire pour la négociation.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-172">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="7d8e8-173">**Non pris en charge**     Le service XMPP ne prend pas en charge TLS.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-173">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="7d8e8-174">**Négociation SASL**     Définit les règles de négociation SASL.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-174">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="7d8e8-175">Un service XMPP peut nécessiter SASL, peut rendre SASL facultatif ou vous pouvez décider de ne pas prendre en charge SASL.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-175">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="7d8e8-176">Si vous choisissez Facultatif, le service XMPP est responsable de la décision sur la négociation obligatoire.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-176">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
          - <span></span>  
            <span data-ttu-id="7d8e8-177">**Obligatoire**     Le service XMPP requiert une négociation SASL.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-177">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="7d8e8-178">**Facultatif**     Le service XMPP indique que SASL est obligatoire pour la négociation.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-178">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="7d8e8-179">**Non pris en charge**     Le service XMPP ne prend pas en charge SASL.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-179">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="7d8e8-180">**Prendre en charge la négociation rappel de serveur** Le processus de négociation rappel de serveur de prise en charge utilise le système DNS (Domain Name System) et un serveur faisant autorité pour vérifier que la demande provenait d’un partenaire XMPP valide.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-180">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="7d8e8-181">Pour ce faire, le serveur d’origine crée un message d’un type spécifique avec une clé rappel générée et recherche le serveur de réception dans le système DNS.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-181">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="7d8e8-182">Le serveur d’origine envoie la clé dans un flux XML à la recherche DNS résultante, vraisemblablement le serveur de réception.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-182">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="7d8e8-183">Lors de la réception de la clé sur le flux XML, le serveur de réception ne répond pas au serveur d’origine, mais envoie la clé à un serveur faisant autorité connu.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-183">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="7d8e8-184">Le serveur faisant autorité vérifie que la clé est valide ou non valide.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-184">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="7d8e8-185">S’il n’est pas valide, le serveur de réception ne répond pas au serveur d’origine.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-185">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="7d8e8-186">Si la clé est valide, le serveur de réception informe le serveur d’origine que l’identité et la clé sont valides et que la conversation peut commencer.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-186">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="7d8e8-187">Il existe deux états valides pour la **négociation de rappel** :</span><span class="sxs-lookup"><span data-stu-id="7d8e8-187">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="7d8e8-188">**True**     Le serveur XMPP est configuré pour utiliser la négociation rappel si une demande doit être reçue d’un serveur d’origine.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-188">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
          - <span></span>  
            <span data-ttu-id="7d8e8-189">**Valeur false**     Le serveur XMPP n’est pas configuré pour utiliser la négociation rappel et si une demande doit être reçue d’un serveur d’origine, elle sera ignorée.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-189">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="7d8e8-190">Cliquez sur **Valider** pour enregistrer vos modifications du site ou de la stratégie de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-190">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="7d8e8-191">Mettre à jour des enregistrements DNS pour la passerelle XMPP de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d8e8-191">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="7d8e8-192">Pour configurer DNS pour la Fédération XMPP, vous devez ajouter l’enregistrement SRV suivant à votre DNS externe : \_ XMPP-Server. \_ TCP.\<domain name\></span><span class="sxs-lookup"><span data-stu-id="7d8e8-192">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\></span></span> <span data-ttu-id="7d8e8-193">L’enregistrement SRV est résolu en un nom de domaine complet du serveur Edge d’accès, avec une valeur de port de 5269.</span><span class="sxs-lookup"><span data-stu-id="7d8e8-193">The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

