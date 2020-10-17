---
title: Affectation d’un certificat d’authentification de serveur à serveur à Lync Server 2013
description: Affectation d’un certificat d’authentification de serveur à serveur à Lync Server 2013.
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
ms.openlocfilehash: 042158167f89dc2b6e743e8db94149d4f1cbc1a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560540"
---
# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a><span data-ttu-id="52924-103">Affectation d’un certificat d’authentification de serveur à serveur à Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52924-103">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52924-104">_**Dernière modification de la rubrique :** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="52924-104">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="52924-105">Pour déterminer si un certificat d’authentification de serveur à serveur a déjà été attribué à Microsoft Lync Server 2013, exécutez la commande suivante à partir de Lync Server 2013 Management Shell :</span><span class="sxs-lookup"><span data-stu-id="52924-105">To determine whether or not a server-to-server authentication certificate has already been assigned to Microsoft Lync Server 2013, run the following command from the Lync Server 2013 Management Shell:</span></span>

    Get-CsCertificate -Type OAuthTokenIssuer

<span data-ttu-id="52924-106">Si aucune information de certificat n’est renvoyée, vous devez affecter un certificat d’émetteur de jeton avant de pouvoir utiliser l’authentification de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="52924-106">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="52924-107">En règle générale, tout certificat Lync Server 2013 peut être utilisé comme certificat OAuthTokenIssuer ; par exemple, votre certificat par défaut Lync Server 2013 peut également être utilisé comme certificat OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="52924-107">As a general rule, any Lync Server 2013 certificate can be used as your OAuthTokenIssuer certificate; for example, your Lync Server 2013 default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="52924-108">(Le certificat OAUthTokenIssuer peut également être n’importe quel certificat de serveur Web qui inclut le nom de votre domaine SIP dans le champ Subject.) Les deux exigences principales pour le certificat utilisé pour l’authentification de serveur à serveur sont les suivantes : 1) le même certificat doit être configuré en tant que certificat OAuthTokenIssuer sur tous vos serveurs frontaux ; et, 2) le certificat doit être d’au moins 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="52924-108">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>

<span data-ttu-id="52924-p102">Si vous n’avez pas de certificat à même de servir pour l’authentification de serveur à serveur, vous pouvez obtenir un nouveau certificat, l’importer, puis l’utiliser pour l’authentification de serveur à serveur. Après avoir demandé et obtenu le nouveau certificat, vous pouvez ensuite ouvrir une session sur l’un de vos serveurs frontaux et passer par une commande Windows PowerShell semblable à celle-ci pour importer et affecter le certificat :</span><span class="sxs-lookup"><span data-stu-id="52924-p102">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication. After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

<span data-ttu-id="52924-p103">Dans la commande précédente, le paramètre Path représente le chemin d’accès complet au fichier du certificat et le paramètre Password correspond au mot de passe ayant été affecté au certificat. Cette procédure ne doit être suivie qu’une seule fois : le service de réplication de Lync Server crée ensuite automatiquement un ensemble de tâches planifiées qui doivent déchiffrer et déployer le certificat sur tous vos serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="52924-p103">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate. This procedure should be run just one time: Lync Server's replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>

<span data-ttu-id="52924-p104">Une autre solution consiste à utiliser un certificat existant comme certificat pour votre authentification de serveur à serveur. (Comme indiqué avant, le certificat par défaut peut être utilisé comme certificat d’authentification de serveur à serveur.) Les deux commandes Windows PowerShell suivantes récupèrent la valeur de la propriété Thumbprint du certificat par défaut, puis utilise la valeur pour faire du certificat par défaut le certificat d’authentification de serveur à serveur :</span><span class="sxs-lookup"><span data-stu-id="52924-p104">Alternatively, you can use an existing certificate as your server-to-server authentication certificate. (As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

<span data-ttu-id="52924-p105">Dans la commande précédente, le certificat récupéré est configuré pour fonctionner comme certificat global d’authentification de serveur à serveur, c’est-à-dire que le certificat est répliqué sur, et utilisé par, tous vos serveurs frontaux. Là encore, cette commande ne doit être exécutée qu’une seule fois et seulement sur l’un de vos serveurs frontaux. Bien que tous les serveurs frontaux doivent utiliser le même certificat, ne configurez pas le certificat OAuthTokenIssuer sur chacun des serveurs frontaux. Configurez-le plutôt une fois, puis laissez le serveur de réplication de Lync Server s’occuper de la copie du certificat sur chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="52924-p105">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers. Again, this command should only be run one time, and only on one of your Front End Servers. Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server. Instead, configure the certificate once, then let Lync Server's replication server take care of copying that certificate to each server.</span></span>

<span data-ttu-id="52924-119">La cmdlet Set-CsCertificate prend le certificat en question et configure immédiatement ce certificat pour agir comme le certificat OAuthTokenIssuer actuel.</span><span class="sxs-lookup"><span data-stu-id="52924-119">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="52924-120">(Lync Server 2013 conserve deux copies d’un type de certificat : le certificat actuel et le certificat précédent.) Si vous avez besoin que le nouveau certificat commence immédiatement à agir en tant que certificat OAuthTokenIssuer, vous devez utiliser la cmdlet Set-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="52924-120">(Lync Server 2013 keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="52924-p107">Vous pouvez aussi passer par l’applet de commande Set-CsCertificate pour « transmettre » un nouveau certificat. « Transmettre » un certificat revient simplement à configurer un nouveau certificat pour qu’il devienne le certificat OAuthTokenIssuer actif à un moment précis. Par exemple, la commande suivante récupère le certificat par défaut puis le configure pour prendre la suite en tant que certificat OAuthTokenIssuer actif à partir du 1er juillet 2012 :</span><span class="sxs-lookup"><span data-stu-id="52924-p107">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate. "Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time. For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2012:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

<span data-ttu-id="52924-124">Le 1er juillet 2012, le nouveau certificat est alors configuré comme certificat OAuthTokenIssuer actif et « l’ancien » certificat OAuthTokenIssuer est configuré en tant que certificat précédent.</span><span class="sxs-lookup"><span data-stu-id="52924-124">On July 1, 2012 the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>

<span data-ttu-id="52924-p108">Si vous ne voulez pas utiliser Windows PowerShell, vous pouvez aussi faire appel à la console MMC Certificats pour exporter un certificat d’un serveur frontal puis l’importer sur tous vos autres serveurs frontaux. Assurez-vous dans ce cas d’exporter la clé privée en plus du certificat même.</span><span class="sxs-lookup"><span data-stu-id="52924-p108">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers. If you do this, make sure that you export the private key along with the certificate itself.</span></span>

<div>


> [!WARNING]
> <span data-ttu-id="52924-127">Dans ce cas, vous devez effectuer la procédure sur chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="52924-127">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="52924-128">Lorsque vous exportez et importez des certificats de cette manière, Lync Server 2013 ne réplique pas ce certificat sur chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="52924-128">When exporting and importing certificates in this manner Lync Server 2013 will not replicate that certificate to each Front End Server.</span></span>



</div>

<span data-ttu-id="52924-129">Une fois que le certificat a été importé sur tous vos serveurs frontaux, ce certificat peut être affecté à l’aide de l’Assistant Déploiement de Lync Server au lieu de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="52924-129">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Lync Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="52924-130">Pour affecter un certificat par le biais de l’Assistant Déploiement, effectuez les étapes suivantes sur un ordinateur où l’Assistant est installé :</span><span class="sxs-lookup"><span data-stu-id="52924-130">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>

1.  <span data-ttu-id="52924-131">Cliquez successivement sur Démarrer, sur tous les programmes, sur **Microsoft Lync server 2013**, puis sur **Assistant Déploiement Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="52924-131">Click Start, click All Programs, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="52924-132">Dans l’Assistant Déploiement, cliquez sur **Installer ou mettre à jour le système Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="52924-132">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="52924-133">Sur la page Microsoft Lync Server 2013, cliquez sur le bouton **exécuter** sous le titre **étape 3 : demander, installer ou assigner des certificats**.</span><span class="sxs-lookup"><span data-stu-id="52924-133">On the Microsoft Lync Server 2013 page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="52924-134">(Remarque : Si vous avez déjà installé des certificats sur cet ordinateur, le bouton **Exécuter** s’appelle **Réexécuter**.)</span><span class="sxs-lookup"><span data-stu-id="52924-134">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>

4.  <span data-ttu-id="52924-135">Dans l’Assistant Certificat, sélectionnez le certificat **OAuthTokenIssuer**, puis cliquez sur **Affecter**.</span><span class="sxs-lookup"><span data-stu-id="52924-135">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>

5.  <span data-ttu-id="52924-136">Dans l’Assistant Assignation de certificat, dans la page **Assignation de certificat**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="52924-136">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>

6.  <span data-ttu-id="52924-137">Dans la page **Magasin de certificats**, sélectionnez le certificat à utiliser pour l’authentification de serveur à serveur, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="52924-137">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>

7.  <span data-ttu-id="52924-138">Dans la page Résumé de l’affectation du certificat, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="52924-138">On the Certificate Assignment Summary page, click **Next**.</span></span>

8.  <span data-ttu-id="52924-139">Dans la page Exécution de commandes, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="52924-139">On the Executing Commands page, click **Finish**.</span></span>

9.  <span data-ttu-id="52924-140">Fermez l’Assistant Certificat et l’Assistant Déploiement.</span><span class="sxs-lookup"><span data-stu-id="52924-140">Close the Certificate Wizard and the Deployment Wizard.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

