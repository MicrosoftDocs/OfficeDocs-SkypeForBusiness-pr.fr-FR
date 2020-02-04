---
title: Attribution d’un certificat d’authentification de serveur à serveur à Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06372be3808f3855bc0172cc408308a0c9c9cab2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a><span data-ttu-id="cb367-102">Attribution d’un certificat d’authentification de serveur à serveur à Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb367-102">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb367-103">_**Dernière modification de la rubrique :** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="cb367-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="cb367-104">Pour déterminer si un certificat d’authentification de serveur à serveur est déjà attribué à Microsoft Lync Server 2013, exécutez la commande suivante à partir de Lync Server 2013 Management Shell :</span><span class="sxs-lookup"><span data-stu-id="cb367-104">To determine whether or not a server-to-server authentication certificate has already been assigned to Microsoft Lync Server 2013, run the following command from the Lync Server 2013 Management Shell:</span></span>

    Get-CsCertificate -Type OAuthTokenIssuer

<span data-ttu-id="cb367-105">Si aucune information de certificat n’est renvoyée, vous devez attribuer un certificat de l’émetteur de jeton pour pouvoir utiliser l’authentification de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="cb367-105">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="cb367-106">En règle générale, tout certificat 2013 de Lync Server peut être utilisé comme certificat OAuthTokenIssuer. par exemple, vous pouvez également utiliser votre certificat par défaut Lync Server 2013 comme certificat OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="cb367-106">As a general rule, any Lync Server 2013 certificate can be used as your OAuthTokenIssuer certificate; for example, your Lync Server 2013 default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="cb367-107">(Le certificat OAUthTokenIssuer peut également être un certificat de serveur Web incluant le nom de votre domaine SIP dans le champ Subject.) Les deux conditions principales requises pour le certificat utilisé pour l’authentification de serveur à serveur sont les suivantes : 1) le même certificat doit être configuré en tant que certificat OAuthTokenIssuer sur tous les serveurs frontaux. et 2) le certificat doit comporter au moins 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="cb367-107">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>

<span data-ttu-id="cb367-108">Si vous n’avez pas de certificat à même de servir pour l’authentification de serveur à serveur, vous pouvez obtenir un nouveau certificat, l’importer, puis l’utiliser pour l’authentification de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="cb367-108">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication.</span></span> <span data-ttu-id="cb367-109">Après avoir demandé et obtenu le nouveau certificat, vous pouvez vous connecter à l’un de vos serveurs frontaux et utiliser une commande Windows PowerShell similaire à celle-ci pour importer et attribuer ce certificat :</span><span class="sxs-lookup"><span data-stu-id="cb367-109">After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

<span data-ttu-id="cb367-110">Dans la commande précédente, le paramètre Path représente le chemin d’accès complet au fichier du certificat et le paramètre Password correspond au mot de passe affecté au certificat.</span><span class="sxs-lookup"><span data-stu-id="cb367-110">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate.</span></span> <span data-ttu-id="cb367-111">Cette procédure doit être exécutée une seule fois : le service de réplication de Lync Server créera automatiquement un ensemble de tâches planifiées qui décryptera et déploiera le certificat sur tous vos serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="cb367-111">This procedure should be run just one time: Lync Server's replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>

<span data-ttu-id="cb367-112">Une autre solution consiste à utiliser un certificat existant comme certificat pour votre authentification de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="cb367-112">Alternatively, you can use an existing certificate as your server-to-server authentication certificate.</span></span> <span data-ttu-id="cb367-113">(Comme indiqué, le certificat par défaut peut être utilisé en tant que certificat d’authentification de serveur à serveur.) La paire de commandes Windows PowerShell suivantes récupère la valeur de la propriété d’empreinte du certificat par défaut, puis utilise cette valeur pour définir le certificat par défaut du certificat d’authentification serveur à serveur :</span><span class="sxs-lookup"><span data-stu-id="cb367-113">(As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

<span data-ttu-id="cb367-114">Dans la commande précédente, le certificat récupéré est configuré pour fonctionner en tant que certificat d’authentification serveur à serveur global ; Cela signifie que le certificat sera répliqué vers et utilisé par tous vos serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="cb367-114">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers.</span></span> <span data-ttu-id="cb367-115">Là encore, cette commande ne doit être exécutée qu’une seule fois et sur l’un de vos serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="cb367-115">Again, this command should only be run one time, and only on one of your Front End Servers.</span></span> <span data-ttu-id="cb367-116">Même si tous les serveurs front-end doivent utiliser le même certificat, vous ne devez pas configurer le certificat OAuthTokenIssuer sur chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="cb367-116">Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server.</span></span> <span data-ttu-id="cb367-117">Au lieu de cela, configurez le certificat une seule fois, puis faites en sorte que le serveur de réplication de Lync Server prenne en charge la copie de ce certificat sur chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="cb367-117">Instead, configure the certificate once, then let Lync Server's replication server take care of copying that certificate to each server.</span></span>

<span data-ttu-id="cb367-118">La cmdlet Set-CsCertificate prend le certificat en question et configure immédiatement ce certificat pour agir en tant que certificat OAuthTokenIssuer actuel.</span><span class="sxs-lookup"><span data-stu-id="cb367-118">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="cb367-119">(Lync Server 2013 conserve deux copies d’un type de certificat : le certificat actuel et le certificat précédent.) Si vous avez besoin que le nouveau certificat commence immédiatement à fonctionner en tant que certificat OAuthTokenIssuer, vous devez utiliser l’applet de certification Set-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="cb367-119">(Lync Server 2013 keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="cb367-120">Vous pouvez également utiliser l’applet de commande Set-CsCertificate pour « transmettre » un nouveau certificat.</span><span class="sxs-lookup"><span data-stu-id="cb367-120">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate.</span></span> <span data-ttu-id="cb367-121">« Transmettre » un certificat revient simplement à configurer un nouveau certificat pour qu’il devienne le certificat OAuthTokenIssuer actif à un moment précis.</span><span class="sxs-lookup"><span data-stu-id="cb367-121">"Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time.</span></span> <span data-ttu-id="cb367-122">Par exemple, cette commande récupère le certificat par défaut, puis configure ce certificat pour prendre le contrôle en tant que certificat OAuthTokenIssuer actuel le 1er juillet 2012 :</span><span class="sxs-lookup"><span data-stu-id="cb367-122">For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2012:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

<span data-ttu-id="cb367-123">Le 1er juillet, 2012 le nouveau certificat sera configuré comme le certificat OAuthTokenIssuer actuel et le certificat OAuthTokenIssuer "Old" sera configuré comme certificat précédent.</span><span class="sxs-lookup"><span data-stu-id="cb367-123">On July 1, 2012 the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>

<span data-ttu-id="cb367-124">Si vous ne voulez pas utiliser Windows PowerShell, vous pouvez également utiliser la console MMC Certificats pour exporter un certificat à partir d’un serveur frontal, puis importer ce certificat sur tous les autres serveurs front-end.</span><span class="sxs-lookup"><span data-stu-id="cb367-124">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers.</span></span> <span data-ttu-id="cb367-125">En pareil cas, veillez à exporter la clé privée en plus du certificat proprement dit.</span><span class="sxs-lookup"><span data-stu-id="cb367-125">If you do this, make sure that you export the private key along with the certificate itself.</span></span>

<div>


> [!WARNING]
> <span data-ttu-id="cb367-126">Dans ce cas, la procédure doit être effectuée sur chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="cb367-126">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="cb367-127">Lors de l’exportation et de l’importation de certificats de cette manière, Lync Server 2013 ne dupliquera pas ce certificat sur chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="cb367-127">When exporting and importing certificates in this manner Lync Server 2013 will not replicate that certificate to each Front End Server.</span></span>



</div>

<span data-ttu-id="cb367-128">Après l’importation du certificat sur tous vos serveurs frontaux, ce certificat peut ensuite être attribué à l’aide de l’Assistant Déploiement de Lync Server au lieu de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb367-128">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Lync Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="cb367-129">Pour affecter un certificat par le biais de l’Assistant Déploiement, effectuez la procédure ci-dessous sur un ordinateur sur lequel l’Assistant est installé :</span><span class="sxs-lookup"><span data-stu-id="cb367-129">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>

1.  <span data-ttu-id="cb367-130">Cliquez sur Démarrer, sur tous les programmes, sur **Microsoft Lync server 2013**, puis sur **Assistant Déploiement de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cb367-130">Click Start, click All Programs, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="cb367-131">Dans l’Assistant Déploiement, cliquez sur **installer ou mettre à jour le système serveur Lync**.</span><span class="sxs-lookup"><span data-stu-id="cb367-131">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="cb367-132">Sur la page Microsoft Lync Server 2013, cliquez sur le bouton **exécuter** sous le titre **étape 3 : demander, installer ou affecter des certificats**.</span><span class="sxs-lookup"><span data-stu-id="cb367-132">On the Microsoft Lync Server 2013 page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="cb367-133">(Remarque : Si vous avez déjà installé des certificats sur cet ordinateur, le bouton **Exécuter** s’appelle **Réexécuter**.)</span><span class="sxs-lookup"><span data-stu-id="cb367-133">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>

4.  <span data-ttu-id="cb367-134">Dans l’Assistant Certificat, sélectionnez le certificat **OAuthTokenIssuer**, puis cliquez sur **Affecter**.</span><span class="sxs-lookup"><span data-stu-id="cb367-134">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>

5.  <span data-ttu-id="cb367-135">Dans l’Assistant Assignation de certificat, dans la page **Affectation de certificat**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cb367-135">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>

6.  <span data-ttu-id="cb367-136">Dans la page **Magasin de certificats**, sélectionnez le certificat à utiliser pour l’authentification de serveur à serveur, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cb367-136">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>

7.  <span data-ttu-id="cb367-137">Dans la page Résumé de l’affectation du certificat, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cb367-137">On the Certificate Assignment Summary page, click **Next**.</span></span>

8.  <span data-ttu-id="cb367-138">Dans la page Exécution de commandes, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="cb367-138">On the Executing Commands page, click **Finish**.</span></span>

9.  <span data-ttu-id="cb367-139">Fermez l’Assistant Certificat et l’Assistant Déploiement.</span><span class="sxs-lookup"><span data-stu-id="cb367-139">Close the Certificate Wizard and the Deployment Wizard.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

