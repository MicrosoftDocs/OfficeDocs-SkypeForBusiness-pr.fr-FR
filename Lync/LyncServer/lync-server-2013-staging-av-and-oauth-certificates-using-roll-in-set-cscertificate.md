---
title: Test des certificats AV et OAuth à l’aide de la CsCertificate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a85d39fb80075e4de817c4343040d358ad41eeb5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a><span data-ttu-id="0824a-102">Staging des certificats AV et OAuth dans Lync Server 2013 avec l’utilisation de la CsCertificate</span><span class="sxs-lookup"><span data-stu-id="0824a-102">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0824a-103">_**Dernière modification de la rubrique :** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="0824a-103">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="0824a-104">Les communications audio/vidéo (A/V) sont un composant clé de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0824a-104">Audio/Video (A/V) communications is a key component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="0824a-105">Les fonctionnalités telles que le partage d’application et la conférence audio et vidéo s’appuient sur les certificats attribués au service Edge A/V, en particulier le service d’authentification A/V.</span><span class="sxs-lookup"><span data-stu-id="0824a-105">Features such as application sharing and audio and video conferencing rely on the certificates assigned to the A/V Edge service, specifically the A/V Authentication service.</span></span>

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P><span data-ttu-id="0824a-106">Cette nouvelle fonctionnalité est conçue pour fonctionner avec le service Edge A/V et le certificat <EM>OAuthTokenIssuer</EM> .</span><span class="sxs-lookup"><span data-stu-id="0824a-106">This new feature is designed to work for the A/V Edge service and the <EM>OAuthTokenIssuer</EM> certificate.</span></span> <span data-ttu-id="0824a-107">D’autres types de certificats peuvent être mis en service avec le service Edge A/V et le type de certificat OAuth, mais ils ne bénéficieront pas du comportement de coexistence du certificat de service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="0824a-107">Other certificate types can be provisioned along with the A/V Edge service and OAuth certificate type, but will not benefit from the coexistence behavior that the A/V Edge service certificate will.</span></span></P>
> <LI>
> <P><span data-ttu-id="0824a-108">Les applets de commande Lync Server Management Shell PowerShell utilisées pour gérer les certificats Microsoft Lync Server 2013 font référence au certificat de service Edge A/V comme type de certificat <EM>AudioVideoAuthentication</EM> et au certificat OAuthServer en tant que type <EM>OAuthTokenIssuer</EM>.</span><span class="sxs-lookup"><span data-stu-id="0824a-108">The Lync Server Management Shell PowerShell cmdlets used to manage Microsoft Lync Server 2013 certificates refers to the A/V Edge service certificate as the <EM>AudioVideoAuthentication</EM> certificate type and the OAuthServer certificate as type <EM>OAuthTokenIssuer</EM>.</span></span> <span data-ttu-id="0824a-109">Pour le reste de cette rubrique et pour identifier les certificats de manière unique, ils seront désignés par le même type d’identificateur, <EM>AudioVideoAuthentication</EM> et <EM>OAuthTokenIssuer</EM>.</span><span class="sxs-lookup"><span data-stu-id="0824a-109">For the rest of this topic and to uniquely identify the certificates, they will be referred to by the same identifier type, <EM>AudioVideoAuthentication</EM> and <EM>OAuthTokenIssuer</EM>.</span></span></P></LI></OL>



</div>

<span data-ttu-id="0824a-110">Le service d’authentification A/V est responsable de l’émission des jetons utilisés par les clients et autres consommateurs A/V.</span><span class="sxs-lookup"><span data-stu-id="0824a-110">The A/V Authentication service is responsible for issuing tokens that are used by clients and other A/V consumers.</span></span> <span data-ttu-id="0824a-111">Les jetons sont générés à partir des attributs du certificat et l’expiration de celui-ci entraîne la perte de la connexion et la nécessité de se reconnecter avec un nouveau jeton généré par le nouveau certificat.</span><span class="sxs-lookup"><span data-stu-id="0824a-111">The tokens are generated from attributes on the certificate, and when the certificate expires, loss of connection and requirement to rejoin with a new token generated by the new certificate will result.</span></span> <span data-ttu-id="0824a-112">Une nouvelle fonctionnalité de Lync Server 2013 permet d’éviter ce problème : la possibilité de mettre en place un nouveau certificat avant l’expiration de l’ancien et de faire en sorte que les deux certificats continuent de fonctionner pendant un certain temps.</span><span class="sxs-lookup"><span data-stu-id="0824a-112">A new feature in Lync Server 2013 will alleviate this problem – the ability to stage a new certificate in advance of the old one expiring and allowing both certificates to continue to function for a period of time.</span></span> <span data-ttu-id="0824a-113">Cette fonctionnalité utilise la fonctionnalité mise à jour dans l’applet de commande Set-CsCertificate Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0824a-113">This feature uses updated functionality in the Set-CsCertificate Lync Server Management Shell cmdlet.</span></span> <span data-ttu-id="0824a-114">Le nouveau paramètre –Roll, avec le paramètre –EffectiveDate existant, placera le nouveau certificat AudioVideoAuthentication dans le magasin de certificats.</span><span class="sxs-lookup"><span data-stu-id="0824a-114">The new parameter –Roll, with the existing parameter –EffectiveDate, will place the new AudioVideoAuthentication certificate in the certificate store.</span></span> <span data-ttu-id="0824a-115">L’ancien certificat AudioVideoAuthentication sera conservé pour permettre la validation des jetons émis.</span><span class="sxs-lookup"><span data-stu-id="0824a-115">The older AudioVideoAuthentication certificate will still remain for issued tokens to be validated against.</span></span> <span data-ttu-id="0824a-116">Après la mise en place du nouveau certificat AudioVideoAuthentication, la série d’événements suivante se produira :</span><span class="sxs-lookup"><span data-stu-id="0824a-116">Beginning with putting the new AudioVideoAuthentication certificate in place, the following series of events will occur:</span></span>

<div>


> [!TIP]
> <span data-ttu-id="0824a-117">À l’aide des applets de commande Lync Server Management Shell pour la gestion des certificats, vous pouvez demander des certificats distincts et distincts pour chaque objectif sur le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="0824a-117">Using the Lync Server Management Shell cmdlets for managing certificates, you can request separate and distinct certificates for each purpose on the Edge Server.</span></span> <span data-ttu-id="0824a-118">L’utilisation de l’Assistant certificat dans l’Assistant Déploiement de Lync Server vous aide à créer des certificats, mais il s’agit généralement du type <STRONG>par défaut</STRONG> qui associe toutes les utilisations de certificat pour le serveur Edge à un seul certificat.</span><span class="sxs-lookup"><span data-stu-id="0824a-118">Using the Certificate Wizard in the Lync Server Deployment Wizard assists you in creating certificates, but is typically of the <STRONG>default</STRONG> type which couples all certificate uses for the Edge Server onto a single certificate.</span></span> <span data-ttu-id="0824a-119">La pratique recommandée si vous souhaitez utiliser la fonctionnalité de certificat propagé consiste à dissocier le certificat AudioVideoAuthentication des autres finalités du certificat.</span><span class="sxs-lookup"><span data-stu-id="0824a-119">The recommended practice if you are going to use the rolling certificate feature is to decouple the AudioVideoAuthentication certificate from the other certificate purposes.</span></span> <span data-ttu-id="0824a-120">Vous pouvez configurer et créer un certificat transitoire de type Default, mais seule la partie AudioVideoAuthentication du certificat combiné bénéficiera de cette création transitoire.</span><span class="sxs-lookup"><span data-stu-id="0824a-120">You can provision and stage a certificate of the Default type, but only the AudioVideoAuthentication portion of the combined certificate will benefit from the staging.</span></span> <span data-ttu-id="0824a-121">Un utilisateur impliqué dans (par exemple) une conversation de messagerie instantanée lorsque le certificat expire doit se déconnecter et se reconnecter pour utiliser le nouveau certificat associé au service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="0824a-121">A user involved in (for example) an instant messaging conversation when the certificate expires will need to log out and log back in to make use of the new certificate associated with the Access Edge service.</span></span> <span data-ttu-id="0824a-122">Un comportement similaire se produira pour un utilisateur impliqué dans une conférence Web à l’aide du service Edge de conférence Web.</span><span class="sxs-lookup"><span data-stu-id="0824a-122">Similar behavior will occur for a user involved in a Web conference using the Web Conferencing Edge service.</span></span> <span data-ttu-id="0824a-123">Le certificat OAuthTokenIssuer est un type spécifique partagé sur tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="0824a-123">The OAuthTokenIssuer certificate is a specific type that is shared across all servers.</span></span> <span data-ttu-id="0824a-124">Vous créez et gérez le certificat à un emplacement et le certificat est stocké dans le magasin central de gestion pour tous les autres serveurs.</span><span class="sxs-lookup"><span data-stu-id="0824a-124">You create and manage the certificate in one place and the certificate is stored in the Central Management store for all other servers.</span></span>



</div>

<span data-ttu-id="0824a-125">Des informations supplémentaires sont nécessaires pour bien comprendre vos options et spécifications quand vous utilisez l’applet de commande Set-CsCertificate, notamment quand vous l’utilisez pour créer des certificats transitoires avant que le certificat actuel n’expire.</span><span class="sxs-lookup"><span data-stu-id="0824a-125">Additional detail is needed to fully understand your options and requirements when using the Set-CsCertificate cmdlet and using it to stage certificates prior to the current certificate expiring.</span></span> <span data-ttu-id="0824a-126">Le paramètre –Roll est important, mais n’a essentiellement qu’une seule utilité.</span><span class="sxs-lookup"><span data-stu-id="0824a-126">The –Roll parameter is important, but essentially single purpose.</span></span> <span data-ttu-id="0824a-127">Si vous la définissez en tant que paramètre, vous indiquez à Set-CsCertificate que vous allez fournir des informations sur le certificat qui sera affecté défini par – type (par exemple AudioVideoAuthentication et OAuthTokenIssuer), lorsque le certificat deviendra effectif défini par – EffectiveDate.</span><span class="sxs-lookup"><span data-stu-id="0824a-127">If you define it as a parameter, you are telling Set-CsCertificate that you will be providing information about the certificate that will be affected defined by –Type (for example AudioVideoAuthentication and OAuthTokenIssuer), when the certificate will become effective defined by –EffectiveDate.</span></span>

<span data-ttu-id="0824a-128">**-Roulier :** Le paramètre – ROLLBACK est obligatoire et comporte des dépendances qui doivent être fournies avec lui.</span><span class="sxs-lookup"><span data-stu-id="0824a-128">**-Roll:** The –Roll parameter is required and has dependencies that must be supplied along with it.</span></span> <span data-ttu-id="0824a-129">Paramètres requis pour définir entièrement les certificats qui seront affectés et la façon dont ils seront appliqués :</span><span class="sxs-lookup"><span data-stu-id="0824a-129">Required parameters to fully define which certificates will be affected and how they will be applied:</span></span>

<span data-ttu-id="0824a-130">**-EffectiveDate :** Le paramètre – EffectiveDate définit quand le nouveau certificat sera co-actif avec le certificat actuel.</span><span class="sxs-lookup"><span data-stu-id="0824a-130">**-EffectiveDate:** The parameter –EffectiveDate defines when the new certificate will become co-active with the current certificate.</span></span> <span data-ttu-id="0824a-131">Le – EffectiveDate peut être proche de la date d’expiration du certificat actuel, ou il peut s’agir d’une période plus longue.</span><span class="sxs-lookup"><span data-stu-id="0824a-131">The –EffectiveDate can be close to the expiry time of the current certificate, or it can be a longer period of time.</span></span> <span data-ttu-id="0824a-132">Un minimum recommandé – EffectiveDate pour le certificat AudioVideoAuthentication serait de 8 heures, ce qui correspond à la durée de vie du jeton par défaut pour les jetons de service Edge AV émis à l’aide du certificat AudioVideoAuthentication.</span><span class="sxs-lookup"><span data-stu-id="0824a-132">A recommended minimum –EffectiveDate for the AudioVideoAuthentication certificate would be 8 hours, which is the default token lifetime for AV Edge service tokens issued using the AudioVideoAuthentication certificate.</span></span>

<span data-ttu-id="0824a-p109">Lors de la création de certificats OAuthTokenIssuer transitoires, l’heure d’avance (recouvrement) doit répondre à différentes spécifications pour que le certificat puisse entrer en vigueur. Le temps d’avance minimal du certificat OAuthTokenIssuer doit être de 24 heures avant l’heure d’expiration du certificat en cours. L’heure d’avance étendue pour la coexistence est due aux autres rôles de serveur qui dépendent du certificat OAuthTokenIssuer (Exchange Server, par exemple), qui a une durée de conservation supérieure pour les clés de chiffrement et d’authentification créées à l’aide de certificats.</span><span class="sxs-lookup"><span data-stu-id="0824a-p109">When staging OAuthTokenIssuer certificates, there are different requirements for the lead time before the certificate can become effective. The minimum time that the OAuthTokenIssuer certificate should have for its lead time is 24 hours before the expiration time of the current certificate. The extended lead time for the coexistence is because of other server roles that are dependent on the OAuthTokenIssuer certificate (Exchange Server, for example) which has a longer retention time for certificate created authentication and encryption key materials.</span></span>

<span data-ttu-id="0824a-136">**-Empreinte :** L’empreinte numérique est un attribut du certificat propre à ce certificat.</span><span class="sxs-lookup"><span data-stu-id="0824a-136">**-Thumbprint:** The thumbprint is an attribute on the certificate that is unique to that certificate.</span></span> <span data-ttu-id="0824a-137">Le paramètre – empreinte numérique est utilisé pour identifier le certificat qui sera affecté par les actions de l’applet de commande Set-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="0824a-137">The –Thumbprint parameter is used to identify the certificate that will be affected by the actions of the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="0824a-138">**-Type :** Le paramètre – type peut accepter un seul type d’utilisation de certificat ou une liste de types d’utilisation de certificats séparés par des virgules.</span><span class="sxs-lookup"><span data-stu-id="0824a-138">**-Type:** The –Type parameter can accept a single certificate usage type or a comma separated list of certificate usage types.</span></span> <span data-ttu-id="0824a-139">Les types de certificat sont ceux qui identifient l’applet de commande et le serveur en quoi consiste l’objectif du certificat.</span><span class="sxs-lookup"><span data-stu-id="0824a-139">The certificate types are those that identify to the cmdlet and to the server what the purpose of the certificate is.</span></span> <span data-ttu-id="0824a-140">Par exemple, tapez AudioVideoAuthentication est destiné à être utilisé par le service Edge A/V et le service d’authentification antivirus.</span><span class="sxs-lookup"><span data-stu-id="0824a-140">For example, type AudioVideoAuthentication is for use by the A/V Edge service and the AV Authentication service.</span></span> <span data-ttu-id="0824a-141">Si vous décidez d’organiser et de mettre en service des certificats d’un type différent en même temps, vous devez prendre en compte le délai d’exécution effectif minimal le plus long pour les certificats.</span><span class="sxs-lookup"><span data-stu-id="0824a-141">If you decide to stage and provision certificates of a different type at the same time, you must consider the longest required minimum effective lead time for the certificates.</span></span> <span data-ttu-id="0824a-142">Par exemple, vous devez organiser les certificats de type AudioVideoAuthentication et OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="0824a-142">For example, you need to stage certificates of type AudioVideoAuthentication and OAuthTokenIssuer.</span></span> <span data-ttu-id="0824a-143">Votre minimum – EffectiveDate doit être le plus grand des deux certificats, dans ce cas l’OAuthTokenIssuer, dont le délai minimal est de 24 heures.</span><span class="sxs-lookup"><span data-stu-id="0824a-143">Your minimum –EffectiveDate must be the greater of the two certificates, in this case the OAuthTokenIssuer, which has a minimum lead time of 24 hours.</span></span> <span data-ttu-id="0824a-144">Si vous ne souhaitez pas préparer le certificat AudioVideoAuthentication avec une période de temps de 24 heures, préparez-le séparément avec un EffectiveDate qui répond davantage à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="0824a-144">If you do not want to stage the AudioVideoAuthentication certificate with a lead time of 24 hours, stage it separately with an EffectiveDate that is more to your requirements.</span></span>

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="0824a-145">Pour mettre à jour ou renouveler un certificat de service Edge A/V avec les paramètres a-roulier et-EffectiveDate</span><span class="sxs-lookup"><span data-stu-id="0824a-145">To update or renew an A/V Edge service certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="0824a-146">Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="0824a-146">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="0824a-147">Demandez un renouvellement ou un nouveau certificat AudioVideoAuthentication avec une clé privée exportable pour le certificat existant sur le service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="0824a-147">Request a renewal or new AudioVideoAuthentication certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="0824a-148">Importez le nouveau certificat AudioVideoAuthentication sur le serveur Edge et sur tous les autres serveurs Edge de votre pool (si vous disposez d’un pool déployé).</span><span class="sxs-lookup"><span data-stu-id="0824a-148">Import the new AudioVideoAuthentication certificate to the Edge Server and all other Edge Server in your pool (if you have a pool deployed).</span></span>

4.  <span data-ttu-id="0824a-149">Configurez le certificat importé à l’aide de l’applet de commande Set-CsCertificate et utilisez le paramètre –Roll avec le paramètre –EffectiveDate.</span><span class="sxs-lookup"><span data-stu-id="0824a-149">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter.</span></span> <span data-ttu-id="0824a-150">La date d’effet doit être définie comme étant l’heure d’expiration du certificat actuel (14:00:00 ou 2:00:00 PM) moins la durée de vie du jeton, dont la valeur par défaut est de huit heures.</span><span class="sxs-lookup"><span data-stu-id="0824a-150">The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus token lifetime (by default eight hours).</span></span> <span data-ttu-id="0824a-151">Cela nous donne un temps où le certificat doit être défini sur actif et est la chaîne \<\>– EFFECTIVEDATE : « 7/22/2012 6:00:00 AM ».</span><span class="sxs-lookup"><span data-stu-id="0824a-151">This gives us a time that the certificate must be set to active, and is the –EffectiveDate \<string\>: “7/22/2012 6:00:00 AM”.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="0824a-152">Pour un pool de serveurs Edge, tous les certificats AudioVideoAuthentication doivent être déployés et configurés par la date et l’heure définies par le paramètre – EffectiveDate du premier certificat déployé afin d’éviter toute interruption possible des communications A/V en raison de l’expiration du certificat ancien avant que tous les jetons client et consommateur aient été renouvelés à l’aide du nouveau certificat.</span><span class="sxs-lookup"><span data-stu-id="0824a-152">For an Edge pool, you must have all AudioVideoAuthentication certificates deployed and provisioned by the date and time defined by the –EffectiveDate parameter of the first certificate deployed to avoid possible A/V communications disruption due to the older certificate expiring before all client and consumer tokens have been renewed using the new certificate.</span></span>

    
    </div>
    
    <span data-ttu-id="0824a-153">Commande Set-CsCertificate avec les paramètres –Roll et –EffectiveTime :</span><span class="sxs-lookup"><span data-stu-id="0824a-153">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="0824a-154">Exemple de commande Set-CsCertificate :</span><span class="sxs-lookup"><span data-stu-id="0824a-154">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="0824a-p113">Le format de la date d’effet doit correspondre à celui du paramètre régional et linguistique de votre serveur. Cet exemple utilise le paramètre régional et linguistique Anglais (États-Unis)</span><span class="sxs-lookup"><span data-stu-id="0824a-p113">The EffectiveDate must be formatted to match your server’s region and language settings. The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="0824a-157">Une représentation chronologique constitue un moyen efficace pour mieux comprendre le processus utilisé par Set-CsCertificate, -Roll et –EffectiveDate pour créer un certificat intermédiaire permettant d’émettre de nouveaux jetons AudioVideoAuthentication tout en continuant à utiliser un certificat existant pour valider les jetons AudioVideoAuthentication en cours d’utilisation par les consommateurs.</span><span class="sxs-lookup"><span data-stu-id="0824a-157">To further understand the process that Set-CsCertificate, -Roll, and –EffectiveDate use to stage a new certificate for issuing new AudioVideoAuthentication tokens while still using an existing certificate to validate AudioVideoAuthentication that are in use by consumers, a visual timeline is an effective means of understanding the process.</span></span>

<span data-ttu-id="0824a-158">Dans l’exemple suivant, l’administrateur détermine que le certificat de service Edge A/V doit expirer à 2:00:00 PM le 07/22/2012.</span><span class="sxs-lookup"><span data-stu-id="0824a-158">In the following example, the administrator determines that the A/V Edge service certificate is due to expire at 2:00:00 PM on 07/22/2012.</span></span> <span data-ttu-id="0824a-159">Il demande et reçoit un nouveau certificat et l’importe sur chaque serveur Edge de son pool.</span><span class="sxs-lookup"><span data-stu-id="0824a-159">He requests and receives a new certificate and imports it to each Edge Server in his pool.</span></span> <span data-ttu-id="0824a-160">À 14:00 le 22/07/2012, il commence l’exécution de Get-CsCertificate avec le paramètre –Roll, le paramètre -Thumbprint égal à l’empreinte du nouveau certificat, et le paramètre –EffectiveTime auquel la valeur 07/22/2012 6:00:00 AM a été attribuée.</span><span class="sxs-lookup"><span data-stu-id="0824a-160">At 2 AM on 07/22/2012, he begins running Get-CsCertificate with –Roll, -Thumbprint equal to the thumbprint string of the new certificate, and –EffectiveTime set to 07/22/2012 6:00:00 AM.</span></span> <span data-ttu-id="0824a-161">Il exécute cette commande sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="0824a-161">He runs this command on each Edge Server.</span></span>

<span data-ttu-id="0824a-162">![À l’aide des paramètres rouli et EffectiveDate.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "À l’aide des paramètres rouli et EffectiveDate.")</span><span class="sxs-lookup"><span data-stu-id="0824a-162">![Using the Roll and the EffectiveDate parameters.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Using the Roll and the EffectiveDate parameters.")</span></span>

<span data-ttu-id="0824a-p115">Une fois la date d’effet atteinte (7/22/2012 6:00:00 AM), tous les nouveaux jetons sont émis par le nouveau certificat. Lors de la validation des jetons, ces derniers sont d’abord validés par rapport au nouveau certificat. Si la validation échoue, l’ancien certificat est testé. Le processus consistant à tester le nouveau certificat puis à utiliser l’ancien certificat continuera jusqu’à l’expiration de l’ancien certificat. Une fois celui-ci expiré (22/07/2012 à 14:00:00), les jetons seront uniquement validés par le nouveau certificat. L’ancien certificat peut être supprimé en toute sécurité à l’aide de l’applet de commande Remove-CsCertificate et du paramètre –Previous.</span><span class="sxs-lookup"><span data-stu-id="0824a-p115">When the effective time is reached (7/22/2012 6:00:00 AM), all new tokens are issued by the new certificate. When validating tokens, tokens will first be validated against the new certificate. If the validation fails, the old certificate is tried. The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate. Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate. The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="0824a-169">Pour mettre à jour ou renouveler un certificat OAuthTokenIssuer avec les paramètres –Roll et -EffectiveDate</span><span class="sxs-lookup"><span data-stu-id="0824a-169">To update or renew an OAuthTokenIssuer certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="0824a-170">Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="0824a-170">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="0824a-171">Demandez un renouvellement ou un nouveau certificat OAuthTokenIssuer avec une clé privée exportable pour le certificat existant sur le service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="0824a-171">Request a renewal or new OAuthTokenIssuer certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="0824a-172">Importez le nouveau certificat OAuthTokenIssuer sur un serveur frontal de votre pool (si vous disposez d’un pool déployé).</span><span class="sxs-lookup"><span data-stu-id="0824a-172">Import the new OAuthTokenIssuer certificate to a Front End Server in your pool (if you have a pool deployed).</span></span> <span data-ttu-id="0824a-173">Le certificat OAuthTokenIssuer est répliqué globalement et ne doit être mis à jour et renouvelé que sur les serveurs de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="0824a-173">The OAuthTokenIssuer certificate is replicated globally and only needs to be updated and renewed at any server in your deployment.</span></span> <span data-ttu-id="0824a-174">Le serveur frontal est utilisé à titre d’exemple.</span><span class="sxs-lookup"><span data-stu-id="0824a-174">The Front End Server is used as an example.</span></span>

4.  <span data-ttu-id="0824a-p117">Configurez le certificat importé avec l’applet de commande Set-CsCertificate et utilisez le paramètre –Roll avec le paramètre –EffectiveDate. La date d’effet doit être définie comme heure d’expiration du certificat actuel (14:00:00 ou 2:00:00 PM) moins un minimum de 24 heures.</span><span class="sxs-lookup"><span data-stu-id="0824a-p117">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter. The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus a minimum of 24 hours.</span></span>
    
    <span data-ttu-id="0824a-177">Commande Set-CsCertificate avec les paramètres –Roll et –EffectiveTime :</span><span class="sxs-lookup"><span data-stu-id="0824a-177">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="0824a-178">Exemple de commande Set-CsCertificate :</span><span class="sxs-lookup"><span data-stu-id="0824a-178">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="0824a-p118">Le format de la date d’effet doit correspondre à celui du paramètre régional et linguistique de votre serveur. Cet exemple utilise le paramètre régional et linguistique Anglais (États-Unis)</span><span class="sxs-lookup"><span data-stu-id="0824a-p118">The EffectiveDate must be formatted to match your server’s region and language settings. The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="0824a-p119">Quand la date d’effet est atteinte (7/21/2012 1:00:00 AM), tous les nouveaux jetons sont émis par le nouveau certificat. Lors de la validation des jetons, ces derniers sont d’abord validés par rapport au nouveau certificat. Si la validation échoue, l’ancien certificat est testé. Le processus consistant à tester le nouveau certificat puis à utiliser l’ancien certificat continuera jusqu’à l’expiration de l’ancien certificat. Une fois l’ancien certificat expiré (7/22/2012 2:00:00 PM), les jetons seront uniquement validés par le nouveau certificat. L’ancien certificat peut être supprimé en toute sécurité à l’aide de l’applet de commande Remove-CsCertificate et du paramètre –Previous.</span><span class="sxs-lookup"><span data-stu-id="0824a-p119">When the effective time is reached (7/21/2012 1:00:00 AM), all new tokens are issued by the new certificate. When validating tokens, tokens will first be validated against the new certificate. If the validation fails, the old certificate is tried. The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate. Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate. The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0824a-187">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0824a-187">See Also</span></span>


[<span data-ttu-id="0824a-188">Planification des certificats de serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0824a-188">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="0824a-189">Gestion de l’authentification de serveur à serveur (OAuth) et des applications partenaires dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0824a-189">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[<span data-ttu-id="0824a-190">Configurer des certificats de serveur Edge pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0824a-190">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
<span data-ttu-id="0824a-191">[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0824a-191">[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span></span>  
<span data-ttu-id="0824a-192">[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0824a-192">[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

