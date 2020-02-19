---
title: 'Lync Server 2013 : configuration des certificats pour le directeur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d64eac2708c2b7fc1f0bfd3ab26a9bd38581f54c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a><span data-ttu-id="4aa49-102">Configurer des certificats pour le directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aa49-102">Configure certificates for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4aa49-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="4aa49-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4aa49-104">Lorsque vous exécutez l’Assistant Certificat, veillez à être connecté avec un compte membre d’un groupe auquel les autorisations appropriées ont été octroyées pour le type de modèle de certificat que vous allez utiliser.</span><span class="sxs-lookup"><span data-stu-id="4aa49-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="4aa49-105">Par défaut, une demande de certificat Lync Server 2013 utilisera le modèle de certificat de serveur Web.</span><span class="sxs-lookup"><span data-stu-id="4aa49-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="4aa49-106">Si vous utilisez un compte membre du groupe RTCUniversalServerAdmins pour demander un certificat qui utilise ce modèle, vérifiez que le groupe possède les autorisations d’inscription requises pour utiliser ce modèle.</span><span class="sxs-lookup"><span data-stu-id="4aa49-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="4aa49-107">Chaque directeur requiert un certificat par défaut, un certificat web interne et un certificat web externe.</span><span class="sxs-lookup"><span data-stu-id="4aa49-107">Each Director requires a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="4aa49-108">Pour plus d’informations sur les exigences de certificat pour les directeurs, reportez-vous à [Certificate Requirements for Internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="4aa49-108">For details about the certificate requirements for Directors, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="4aa49-p103">Configurez les certificats de directeur en suivant la procédure ci-dessous. Répétez la procédure pour chaque directeur. Les étapes de cette procédure expliquent comment configurer un certificat à partir d’une autorité interne de certification racine d’entreprise déployée par votre organisation et avec le traitement des requêtes hors connexion. Pour plus d’informations sur l’obtention de certificats issus d’une autorité de certification externe, contactez votre équipe de support.</span><span class="sxs-lookup"><span data-stu-id="4aa49-p103">Use the following procedure to configure Director certificates. Repeat the procedure for each Director. The steps of this procedure describe how to configure a certificate from an Internal Enterprise Root certification authority (CA) deployed by your organization and with offline request processing. For details about obtaining certificates from an external CA, contact your support team.</span></span>

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a><span data-ttu-id="4aa49-113">Pour configurer les certificats du directeur ou du pool directeur</span><span class="sxs-lookup"><span data-stu-id="4aa49-113">To configure certificates for the Director or Director pool</span></span>

1.  <span data-ttu-id="4aa49-114">Dans l’Assistant Déploiement Lync Server, à côté de **étape 3 : demander, installer ou assigner les certificats**, cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="4aa49-114">In the Lync Server Deployment Wizard, next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span>

2.  <span data-ttu-id="4aa49-115">Dans la page **Assistant Certificat**, cliquez sur **Demander**.</span><span class="sxs-lookup"><span data-stu-id="4aa49-115">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="4aa49-116">Dans la page **Demande de certificat**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4aa49-116">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="4aa49-117">Dans la page **Demandes différées ou immédiates**, acceptez l’option par défaut, **Envoyer la demande immédiatement à une autorité de certification en ligne**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4aa49-117">On the **Delayed or Immediate Requests** page, accept the default **Send the request immediately to an online certification authority** option, and then click **Next**.</span></span>

5.  <span data-ttu-id="4aa49-118">Dans la page **Choisir une autorité de certification**, cliquez sur l’autorité de certification Windows interne voulue, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4aa49-118">On the **Choose a Certification Authority (CA)** page, click the internal Windows certification authority that you want to use, and then click **Next**.</span></span>

6.  <span data-ttu-id="4aa49-119">Dans la page **Compte d’autorité de certification**, indiquez d’autres informations d’identification à utiliser au cas où le compte auquel vous êtes connecté ne dispose pas de l’autorité nécessaire pour demander le certificat, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4aa49-119">On the **Certification Authority Account** page, specify alternate credentials to be used if the account you are logged on with does not have sufficient authority to request the certificate, and then click **Next**.</span></span>

7.  <span data-ttu-id="4aa49-120">Dans la page **Spécifier un autre modèle de certificat**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4aa49-120">On the **Specify Alternate Certificate Template** page, click **Next**.</span></span>

8.  <span data-ttu-id="4aa49-121">Dans la page **Nom et paramètres de sécurité**, vous pouvez indiquer un **nom convivial** et accepter la longueur de clé de 2048 bits, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4aa49-121">On the **Name and Security Settings** page, you can specify a **Friendly Name**, accept the 2048-bit key length, and then click **Next**.</span></span>

9.  <span data-ttu-id="4aa49-122">Dans la page **Informations relatives à l’organisation**, indiquez, si vous le souhaitez, des informations sur l’organisation, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4aa49-122">On the **Organization Information** page, optionally specify organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="4aa49-123">Dans la page **Informations géographiques**, indiquez, si vous le souhaitez, des informations géographiques, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4aa49-123">On the **Geographical Information** page, optionally specify geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="4aa49-124">Dans la page **Nom de sujet / Autres noms de sujet**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4aa49-124">On the **Subject Name / Subject Alternative Names** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4aa49-125">La liste des autres noms de sujet devrait contenir le nom de l’ordinateur sur lequel vous installez le directeur (s’il n’y en a qu’un) ou le nom du pool directeur ainsi que le nom des URL simples configurés pour l’organisation.</span><span class="sxs-lookup"><span data-stu-id="4aa49-125">The subject alternative name list should contain the name of the computer on which you are installing the Director (if a single Director) or the Director pool name, and the simple URL names configured for the organization.</span></span>

    
    </div>

12. <span data-ttu-id="4aa49-126">Dans la page **Paramètre du domaine SIP sur les autres noms du sujet**, sélectionnez **Domaines SIP configurés** pour tous les domaines devant être gérés par le directeur, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4aa49-126">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the **Configured SIP Domains** for all domains that you want the Director to handle, and then click **Next**.</span></span>

13. <span data-ttu-id="4aa49-127">Dans la page **Configurer d’autres noms du sujet supplémentaires**, ajoutez des noms de sujet supplémentaires, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4aa49-127">On the **Configure Additional Subject Alternative Names** page, add any additional required subject alternative names, and then click **Next**.</span></span>

14. <span data-ttu-id="4aa49-128">Dans la page **Résumé de la demande de certificat**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4aa49-128">On the **Certificate Request Summary** page, click **Next**.</span></span>

15. <span data-ttu-id="4aa49-129">Dans la page **Exécution de commandes**, cliquez sur **Suivant** une fois les commandes exécutées.</span><span class="sxs-lookup"><span data-stu-id="4aa49-129">On the **Executing Commands** page, click **Next** after the commands have finished running.</span></span>

16. <span data-ttu-id="4aa49-130">Dans la page **État de la demande de certificat en ligne**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4aa49-130">On the **Online Certificate Request Status** page, click **Finish**.</span></span>

17. <span data-ttu-id="4aa49-131">Dans la page **Assignation de certificat**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4aa49-131">On the **Certificate Assignment** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4aa49-132">Si vous souhaitez afficher le certificat, double-cliquez sur celui-ci dans la liste.</span><span class="sxs-lookup"><span data-stu-id="4aa49-132">if you want to view the certificate, double-click the certificate in the list.</span></span>

    
    </div>

18. <span data-ttu-id="4aa49-133">Dans la page **Résumé de l’affectation du certificat**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4aa49-133">On the **Certificate Assignment Summary** page, click **Next**.</span></span>

19. <span data-ttu-id="4aa49-134">Dans la page **Exécution de commandes**, cliquez sur **Terminer** une fois les commandes exécutées.</span><span class="sxs-lookup"><span data-stu-id="4aa49-134">On the **Executing Commands** page, click **Finish** after the commands have finished running.</span></span>

20. <span data-ttu-id="4aa49-135">Dans la page **Assistant Certificat**, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="4aa49-135">On the **Certificate Wizard** page, click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

