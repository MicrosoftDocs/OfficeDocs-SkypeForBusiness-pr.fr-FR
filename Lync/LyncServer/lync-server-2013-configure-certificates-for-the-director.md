---
title: 'Lync Server 2013 : Configuration des certificats pour le directeur'
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
ms.openlocfilehash: fccab201ee9ab16b0195bc2780c37ab85f0519e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a><span data-ttu-id="e5cea-102">Configuration des certificats pour le directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5cea-102">Configure certificates for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5cea-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="e5cea-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e5cea-104">Lorsque vous exécutez l’Assistant certificat, assurez-vous que vous êtes connecté à l’aide d’un compte associé à un compte qui dispose des autorisations appropriées pour le type de modèle de certificat que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="e5cea-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="e5cea-105">Par défaut, une demande de certificat 2013 Lync Server utilise le modèle de certificat de serveur Web.</span><span class="sxs-lookup"><span data-stu-id="e5cea-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="e5cea-106">Si vous utilisez un compte membre du groupe RTCUniversalServerAdmins pour demander un certificat à l’aide de ce modèle, vérifiez que le groupe a été affecté aux autorisations d’inscription requises pour utiliser ce modèle.</span><span class="sxs-lookup"><span data-stu-id="e5cea-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="e5cea-107">Chaque directeur nécessite un certificat par défaut, un certificat interne Web et un certificat externe Web.</span><span class="sxs-lookup"><span data-stu-id="e5cea-107">Each Director requires a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="e5cea-108">Pour plus d’informations sur les exigences en matière de certificats pour les directeurs, voir exigences relatives aux [certificats pour les serveurs internes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="e5cea-108">For details about the certificate requirements for Directors, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="e5cea-109">Suivez la procédure ci-dessous pour configurer des certificats de réalisateur.</span><span class="sxs-lookup"><span data-stu-id="e5cea-109">Use the following procedure to configure Director certificates.</span></span> <span data-ttu-id="e5cea-110">Répétez cette procédure pour chaque réalisateur.</span><span class="sxs-lookup"><span data-stu-id="e5cea-110">Repeat the procedure for each Director.</span></span> <span data-ttu-id="e5cea-111">Les étapes de cette procédure décrivent comment configurer un certificat à partir d’une autorité de certification racine d’entreprise, déployée par votre organisation et avec le traitement de requête hors connexion.</span><span class="sxs-lookup"><span data-stu-id="e5cea-111">The steps of this procedure describe how to configure a certificate from an Internal Enterprise Root certification authority (CA) deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="e5cea-112">Pour plus d’informations sur l’obtention de certificats auprès d’une autorité de certification externe, contactez votre équipe de support technique.</span><span class="sxs-lookup"><span data-stu-id="e5cea-112">For details about obtaining certificates from an external CA, contact your support team.</span></span>

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a><span data-ttu-id="e5cea-113">Pour configurer des certificats pour le directeur ou le pool de réalisateurs</span><span class="sxs-lookup"><span data-stu-id="e5cea-113">To configure certificates for the Director or Director pool</span></span>

1.  <span data-ttu-id="e5cea-114">Dans l’Assistant Déploiement de Lync Server, en regard de l' **étape 3 : demandez, installez ou attribuez des certificats**, cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="e5cea-114">In the Lync Server Deployment Wizard, next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span>

2.  <span data-ttu-id="e5cea-115">Dans la page **Assistant Certificat**, cliquez sur **Demander**.</span><span class="sxs-lookup"><span data-stu-id="e5cea-115">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="e5cea-116">Dans la page **demande de certificat** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e5cea-116">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="e5cea-117">Dans la page **demandes ultérieures ou immédiates** , acceptez l’option **Envoyer la demande immédiatement à une autorité de certification en ligne** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e5cea-117">On the **Delayed or Immediate Requests** page, accept the default **Send the request immediately to an online certification authority** option, and then click **Next**.</span></span>

5.  <span data-ttu-id="e5cea-118">Dans la page **choisir une autorité de certification** , cliquez sur l’autorité de certification Windows interne que vous voulez utiliser, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e5cea-118">On the **Choose a Certification Authority (CA)** page, click the internal Windows certification authority that you want to use, and then click **Next**.</span></span>

6.  <span data-ttu-id="e5cea-119">Sur la page compte de l' **autorité de certification** , spécifiez d’autres informations d’identification à utiliser si le compte avec lequel vous vous êtes connecté ne dispose pas de l’autorisation suffisant pour demander le certificat, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e5cea-119">On the **Certification Authority Account** page, specify alternate credentials to be used if the account you are logged on with does not have sufficient authority to request the certificate, and then click **Next**.</span></span>

7.  <span data-ttu-id="e5cea-120">Dans la page **spécifier un modèle de certificat secondaire** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e5cea-120">On the **Specify Alternate Certificate Template** page, click **Next**.</span></span>

8.  <span data-ttu-id="e5cea-121">Dans la page **paramètres de nom et de sécurité** , vous pouvez spécifier un **nom convivial**, accepter la longueur de la clé 2048 bits, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e5cea-121">On the **Name and Security Settings** page, you can specify a **Friendly Name**, accept the 2048-bit key length, and then click **Next**.</span></span>

9.  <span data-ttu-id="e5cea-122">Dans la page informations sur l' **organisation** , spécifiez éventuellement les informations sur l’organisation, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e5cea-122">On the **Organization Information** page, optionally specify organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="e5cea-123">Dans la page **informations géographiques** , spécifiez éventuellement des informations géographiques, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e5cea-123">On the **Geographical Information** page, optionally specify geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="e5cea-124">Dans la page **nom du sujet/nom** de l’objet, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e5cea-124">On the **Subject Name / Subject Alternative Names** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e5cea-125">La liste autre nom de l’objet doit contenir le nom de l’ordinateur sur lequel vous installez le directeur (s’il s’agit d’un seul directeur) ou le nom du pool de réalisateurs, ainsi que les noms d’URL simples configurés pour l’organisation.</span><span class="sxs-lookup"><span data-stu-id="e5cea-125">The subject alternative name list should contain the name of the computer on which you are installing the Director (if a single Director) or the Director pool name, and the simple URL names configured for the organization.</span></span>

    
    </div>

12. <span data-ttu-id="e5cea-126">Dans la page Configuration du protocole **SIP sur le nom de l’objet** , sélectionnez les **domaines SIP configurés** pour tous les domaines que le directeur doit gérer, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e5cea-126">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the **Configured SIP Domains** for all domains that you want the Director to handle, and then click **Next**.</span></span>

13. <span data-ttu-id="e5cea-127">Dans la page **configurez** d’autres noms d’objet, ajoutez d’autres noms d’objet requis, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e5cea-127">On the **Configure Additional Subject Alternative Names** page, add any additional required subject alternative names, and then click **Next**.</span></span>

14. <span data-ttu-id="e5cea-128">Dans la page Résumé de la **demande de certificat** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e5cea-128">On the **Certificate Request Summary** page, click **Next**.</span></span>

15. <span data-ttu-id="e5cea-129">Dans la page **exécution des commandes** , cliquez sur **suivant** à la fin de l’exécution de la commande.</span><span class="sxs-lookup"><span data-stu-id="e5cea-129">On the **Executing Commands** page, click **Next** after the commands have finished running.</span></span>

16. <span data-ttu-id="e5cea-130">Dans la page État de la **demande de certificat en ligne** , cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="e5cea-130">On the **Online Certificate Request Status** page, click **Finish**.</span></span>

17. <span data-ttu-id="e5cea-131">Dans la page **affectation de certificat** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e5cea-131">On the **Certificate Assignment** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e5cea-132">pour afficher le certificat, double-cliquez sur le certificat dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e5cea-132">if you want to view the certificate, double-click the certificate in the list.</span></span>

    
    </div>

18. <span data-ttu-id="e5cea-133">Dans la page **Résumé des affectations de certificat** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e5cea-133">On the **Certificate Assignment Summary** page, click **Next**.</span></span>

19. <span data-ttu-id="e5cea-134">Dans la page **exécution des commandes** , cliquez sur **Terminer** une fois l’exécution de la commande terminée.</span><span class="sxs-lookup"><span data-stu-id="e5cea-134">On the **Executing Commands** page, click **Finish** after the commands have finished running.</span></span>

20. <span data-ttu-id="e5cea-135">Dans la page **Assistant Certificat** , cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="e5cea-135">On the **Certificate Wizard** page, click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

