---
title: Test de l’audiovisuel et des certificats OAuth en utilisant Set-CsCertificate
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
ms.openlocfilehash: 583ab13e50cac7c7a8b345a2ea2cf4c4e1e38d7f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a><span data-ttu-id="85293-102">Test de l’audiovisuel et des certificats OAuth dans Lync Server 2013 à l’aide du CsCertificate</span><span class="sxs-lookup"><span data-stu-id="85293-102">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85293-103">_**Dernière modification de la rubrique :** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="85293-103">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="85293-104">Les communications audio/vidéo (A/V) sont un composant clé de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85293-104">Audio/Video (A/V) communications is a key component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="85293-105">Les fonctionnalités telles que le partage d’application et les conférences audio et vidéo sont basées sur les certificats attribués au service Edge A/V, en particulier le service d’authentification A/V.</span><span class="sxs-lookup"><span data-stu-id="85293-105">Features such as application sharing and audio and video conferencing rely on the certificates assigned to the A/V Edge service, specifically the A/V Authentication service.</span></span>

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P><span data-ttu-id="85293-106">Cette nouvelle fonctionnalité est conçue pour fonctionner pour le service Edge A/V et le certificat <EM>OAuthTokenIssuer</EM> .</span><span class="sxs-lookup"><span data-stu-id="85293-106">This new feature is designed to work for the A/V Edge service and the <EM>OAuthTokenIssuer</EM> certificate.</span></span> <span data-ttu-id="85293-107">D’autres types de certificats peuvent être configurés avec le service Edge A/V et le type de certificat OAuth, mais ils ne pourront pas bénéficier du comportement de coexistence du certificat de service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="85293-107">Other certificate types can be provisioned along with the A/V Edge service and OAuth certificate type, but will not benefit from the coexistence behavior that the A/V Edge service certificate will.</span></span></P>
> <LI>
> <P><span data-ttu-id="85293-108">Les applets de certification PowerShell Lync Server Management Shell utilisées pour gérer les certificats Microsoft Lync Server 2013 font référence au certificat de service A/V, comme le type de certificat <EM>AudioVideoAuthentication</EM> et au certificat OAuthServer en tant que type <EM>OAuthTokenIssuer</EM>.</span><span class="sxs-lookup"><span data-stu-id="85293-108">The Lync Server Management Shell PowerShell cmdlets used to manage Microsoft Lync Server 2013 certificates refers to the A/V Edge service certificate as the <EM>AudioVideoAuthentication</EM> certificate type and the OAuthServer certificate as type <EM>OAuthTokenIssuer</EM>.</span></span> <span data-ttu-id="85293-109">Dans la suite de cette rubrique, les certificats seront désignés par le même type d’identificateur, <EM>AudioVideoAuthentication</EM> et <EM>OAuthTokenIssuer</EM> de manière à les identifier de manière unique.</span><span class="sxs-lookup"><span data-stu-id="85293-109">For the rest of this topic and to uniquely identify the certificates, they will be referred to by the same identifier type, <EM>AudioVideoAuthentication</EM> and <EM>OAuthTokenIssuer</EM>.</span></span></P></LI></OL>



</div>

<span data-ttu-id="85293-110">Le service d’authentification A/V est responsable de l’émission des jetons utilisés par les clients et autres consommateurs A/V.</span><span class="sxs-lookup"><span data-stu-id="85293-110">The A/V Authentication service is responsible for issuing tokens that are used by clients and other A/V consumers.</span></span> <span data-ttu-id="85293-111">Les jetons sont générés à partir des attributs du certificat et l’expiration du certificat entraîne la perte de la connexion et la nécessité de se reconnecter avec un nouveau jeton généré par le nouveau certificat.</span><span class="sxs-lookup"><span data-stu-id="85293-111">The tokens are generated from attributes on the certificate, and when the certificate expires, loss of connection and requirement to rejoin with a new token generated by the new certificate will result.</span></span> <span data-ttu-id="85293-112">Pour résoudre ce problème, une nouvelle fonctionnalité de Lync Server 2013 résout le problème : la possibilité de mettre à niveau un nouveau certificat à l’avance de l’ancien et de laisser fonctionner les deux certificats pour une période donnée.</span><span class="sxs-lookup"><span data-stu-id="85293-112">A new feature in Lync Server 2013 will alleviate this problem – the ability to stage a new certificate in advance of the old one expiring and allowing both certificates to continue to function for a period of time.</span></span> <span data-ttu-id="85293-113">Cette fonctionnalité utilise des fonctionnalités mises à jour dans la cmdlet Set-CsCertificate Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="85293-113">This feature uses updated functionality in the Set-CsCertificate Lync Server Management Shell cmdlet.</span></span> <span data-ttu-id="85293-114">Le nouveau paramètre –Roll, avec le paramètre –EffectiveDate existant, placera le nouveau certificat AudioVideoAuthentication dans le magasin de certificats.</span><span class="sxs-lookup"><span data-stu-id="85293-114">The new parameter –Roll, with the existing parameter –EffectiveDate, will place the new AudioVideoAuthentication certificate in the certificate store.</span></span> <span data-ttu-id="85293-115">L’ancien certificat AudioVideoAuthentication sera conservé pour permettre la validation des jetons émis.</span><span class="sxs-lookup"><span data-stu-id="85293-115">The older AudioVideoAuthentication certificate will still remain for issued tokens to be validated against.</span></span> <span data-ttu-id="85293-116">Après la mise en place du nouveau certificat AudioVideoAuthentication, la série d’événements suivante se produira :</span><span class="sxs-lookup"><span data-stu-id="85293-116">Beginning with putting the new AudioVideoAuthentication certificate in place, the following series of events will occur:</span></span>

<div>


> [!TIP]
> <span data-ttu-id="85293-117">À l’aide des applets de certification Lync Server Management Shell pour la gestion des certificats, vous pouvez demander des certificats distincts et distincts à chaque objectif sur le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="85293-117">Using the Lync Server Management Shell cmdlets for managing certificates, you can request separate and distinct certificates for each purpose on the Edge Server.</span></span> <span data-ttu-id="85293-118">L’Assistant Création de certificat de l’Assistant Déploiement de Lync Server vous aide à créer des certificats, mais il s’agit généralement du type <STRONG>par défaut</STRONG> qui combine l’ensemble des certificats pour le serveur de périphérie sur un certificat unique.</span><span class="sxs-lookup"><span data-stu-id="85293-118">Using the Certificate Wizard in the Lync Server Deployment Wizard assists you in creating certificates, but is typically of the <STRONG>default</STRONG> type which couples all certificate uses for the Edge Server onto a single certificate.</span></span> <span data-ttu-id="85293-119">Si vous souhaitez utiliser la fonctionnalité de certificat propagé, la pratique recommandée consiste à dissocier le certificat AudioVideoAuthentication des autres finalités du certificat.</span><span class="sxs-lookup"><span data-stu-id="85293-119">The recommended practice if you are going to use the rolling certificate feature is to decouple the AudioVideoAuthentication certificate from the other certificate purposes.</span></span> <span data-ttu-id="85293-120">Vous pouvez configurer et créer un certificat transitoire de type Default, mais seule la partie AudioVideoAuthentication du certificat combiné bénéficiera de cette création transitoire.</span><span class="sxs-lookup"><span data-stu-id="85293-120">You can provision and stage a certificate of the Default type, but only the AudioVideoAuthentication portion of the combined certificate will benefit from the staging.</span></span> <span data-ttu-id="85293-121">Un utilisateur impliqué dans une conversation de messagerie instantanée alors qu’il expire doit se déconnecter puis se reconnecter pour pouvoir utiliser le nouveau certificat associé au service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="85293-121">A user involved in (for example) an instant messaging conversation when the certificate expires will need to log out and log back in to make use of the new certificate associated with the Access Edge service.</span></span> <span data-ttu-id="85293-122">Un comportement similaire sera observé pour un utilisateur impliqué dans une conférence Web à l’aide du service Edge de conférence Web.</span><span class="sxs-lookup"><span data-stu-id="85293-122">Similar behavior will occur for a user involved in a Web conference using the Web Conferencing Edge service.</span></span> <span data-ttu-id="85293-123">Le certificat OAuthTokenIssuer est un type spécifique partagé sur tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="85293-123">The OAuthTokenIssuer certificate is a specific type that is shared across all servers.</span></span> <span data-ttu-id="85293-124">Vous créez et gérez le certificat à un emplacement unique et le certificat est stocké dans le magasin de gestion central pour tous les autres serveurs.</span><span class="sxs-lookup"><span data-stu-id="85293-124">You create and manage the certificate in one place and the certificate is stored in the Central Management store for all other servers.</span></span>



</div>

<span data-ttu-id="85293-p106">Des informations supplémentaires sont nécessaires pour bien comprendre vos options et spécifications quand vous utilisez l’applet de commande Set-CsCertificate, par exemple, lorsque vous l’utilisez pour créer des certificats transitoires avant que le certificat actuel expire. Le paramètre –Roll est important, mais n’a, en substance, qu’une seule utilité. Si vous le définissez sous forme de paramètre, vous indiquez à Set-CsCertificate que vous fournirez des informations sur le certificat qui sera affecté, d’après le paramètre –Type (par exemple, AudioVideoAuthentication et OAuthTokenIssuer), quand le certificat entrera en vigueur selon le paramètre –EffectiveDate.</span><span class="sxs-lookup"><span data-stu-id="85293-p106">Additional detail is needed to fully understand your options and requirements when using the Set-CsCertificate cmdlet and using it to stage certificates prior to the current certificate expiring. The –Roll parameter is important, but essentially single purpose. If you define it as a parameter, you are telling Set-CsCertificate that you will be providing information about the certificate that will be affected defined by –Type (for example AudioVideoAuthentication and OAuthTokenIssuer), when the certificate will become effective defined by –EffectiveDate.</span></span>

<span data-ttu-id="85293-128">**-Roll :** Le paramètre – Roll est obligatoire et dispose de dépendances qui doivent être fournies conjointement.</span><span class="sxs-lookup"><span data-stu-id="85293-128">**-Roll:** The –Roll parameter is required and has dependencies that must be supplied along with it.</span></span> <span data-ttu-id="85293-129">Paramètres requis pour définir entièrement les certificats qui seront touchés et la manière dont ils sont appliqués :</span><span class="sxs-lookup"><span data-stu-id="85293-129">Required parameters to fully define which certificates will be affected and how they will be applied:</span></span>

<span data-ttu-id="85293-130">**-EffectiveDate :** Le paramètre – EffectiveDate définit le moment où le nouveau certificat devient coactif avec le certificat actuel.</span><span class="sxs-lookup"><span data-stu-id="85293-130">**-EffectiveDate:** The parameter –EffectiveDate defines when the new certificate will become co-active with the current certificate.</span></span> <span data-ttu-id="85293-131">Le – EffectiveDate peut être proche de la date d’expiration du certificat actuel ou bien il peut s’agir d’une période de temps plus longue.</span><span class="sxs-lookup"><span data-stu-id="85293-131">The –EffectiveDate can be close to the expiry time of the current certificate, or it can be a longer period of time.</span></span> <span data-ttu-id="85293-132">Une valeur minimale recommandée – EffectiveDate pour le certificat AudioVideoAuthentication serait de 8 heures, qui correspond à la durée de vie du jeton par défaut pour les jetons de service Edge AV émis à l’aide du certificat AudioVideoAuthentication.</span><span class="sxs-lookup"><span data-stu-id="85293-132">A recommended minimum –EffectiveDate for the AudioVideoAuthentication certificate would be 8 hours, which is the default token lifetime for AV Edge service tokens issued using the AudioVideoAuthentication certificate.</span></span>

<span data-ttu-id="85293-p109">Lors de la création de certificats OAuthTokenIssuer transitoires, l’heure d’avance (recouvrement) doit répondre à différentes spécifications pour que le certificat puisse entrer en vigueur. Le temps d’avance minimal du certificat OAuthTokenIssuer doit être de 24 heures avant l’heure d’expiration du certificat en cours. L’heure d’avance étendue pour la coexistence est due aux autres rôles de serveur qui dépendent du certificat OAuthTokenIssuer (Exchange Server, par exemple), qui possède une durée de conservation supérieure pour les clés de chiffrement et d’authentification créées à l’aide de certificats.</span><span class="sxs-lookup"><span data-stu-id="85293-p109">When staging OAuthTokenIssuer certificates, there are different requirements for the lead time before the certificate can become effective. The minimum time that the OAuthTokenIssuer certificate should have for its lead time is 24 hours before the expiration time of the current certificate. The extended lead time for the coexistence is because of other server roles that are dependent on the OAuthTokenIssuer certificate (Exchange Server, for example) which has a longer retention time for certificate created authentication and encryption key materials.</span></span>

<span data-ttu-id="85293-136">**-Empreinte numérique :** L’empreinte numérique est un attribut du certificat unique de ce certificat.</span><span class="sxs-lookup"><span data-stu-id="85293-136">**-Thumbprint:** The thumbprint is an attribute on the certificate that is unique to that certificate.</span></span> <span data-ttu-id="85293-137">Le paramètre-d’empreinte numérique est utilisé pour identifier le certificat qui sera affecté par les actions de l’applet de certification Set-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="85293-137">The –Thumbprint parameter is used to identify the certificate that will be affected by the actions of the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="85293-138">**-Type :** Le paramètre – type peut accepter un type d’utilisation de certificat unique ou une liste séparée par des virgules des types d’utilisation de certificats.</span><span class="sxs-lookup"><span data-stu-id="85293-138">**-Type:** The –Type parameter can accept a single certificate usage type or a comma separated list of certificate usage types.</span></span> <span data-ttu-id="85293-139">Les types de certificats sont ceux qui identifient l’objet du certificat sur l’applet de certification et sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="85293-139">The certificate types are those that identify to the cmdlet and to the server what the purpose of the certificate is.</span></span> <span data-ttu-id="85293-140">Par exemple, tapez AudioVideoAuthentication doit être utilisé par le service Edge A/V et le service d’authentification AV.</span><span class="sxs-lookup"><span data-stu-id="85293-140">For example, type AudioVideoAuthentication is for use by the A/V Edge service and the AV Authentication service.</span></span> <span data-ttu-id="85293-141">Si vous décidez de mettre en place des certificats d’un type différent en même temps, vous devez prendre en considération le délai d’exécution effectif le plus long requis pour les certificats.</span><span class="sxs-lookup"><span data-stu-id="85293-141">If you decide to stage and provision certificates of a different type at the same time, you must consider the longest required minimum effective lead time for the certificates.</span></span> <span data-ttu-id="85293-142">Par exemple, vous devez organiser des certificats de type AudioVideoAuthentication et OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="85293-142">For example, you need to stage certificates of type AudioVideoAuthentication and OAuthTokenIssuer.</span></span> <span data-ttu-id="85293-143">Le minimum-EffectiveDate doit être le plus important des deux certificats, dans le cas présent OAuthTokenIssuer, dont le délai de 24 heures est minimal.</span><span class="sxs-lookup"><span data-stu-id="85293-143">Your minimum –EffectiveDate must be the greater of the two certificates, in this case the OAuthTokenIssuer, which has a minimum lead time of 24 hours.</span></span> <span data-ttu-id="85293-144">Si vous ne souhaitez pas organiser le certificat AudioVideoAuthentication avec un délai de 24 heures, emphasez-le séparément avec un EffectiveDate qui répond à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="85293-144">If you do not want to stage the AudioVideoAuthentication certificate with a lead time of 24 hours, stage it separately with an EffectiveDate that is more to your requirements.</span></span>

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="85293-145">Pour mettre à jour ou renouveler un certificat de service Edge A/V à l’aide de paramètres a-roll et EffectiveDate</span><span class="sxs-lookup"><span data-stu-id="85293-145">To update or renew an A/V Edge service certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="85293-146">Connectez-vous à l’ordinateur local en tant que membre du groupe administrateurs.</span><span class="sxs-lookup"><span data-stu-id="85293-146">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="85293-147">Demandez un renouvellement ou un nouveau certificat AudioVideoAuthentication avec la clé privée exportable pour le certificat existant sur le service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="85293-147">Request a renewal or new AudioVideoAuthentication certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="85293-148">Importez le nouveau certificat AudioVideoAuthentication sur le serveur Edge et sur tous les autres serveurs Edge de votre pool (si vous avez déployé un pool).</span><span class="sxs-lookup"><span data-stu-id="85293-148">Import the new AudioVideoAuthentication certificate to the Edge Server and all other Edge Server in your pool (if you have a pool deployed).</span></span>

4.  <span data-ttu-id="85293-149">Configurez le certificat importé à l’aide de l’applet de commande Set-CsCertificate et utilisez le paramètre –Roll avec le paramètre –EffectiveDate.</span><span class="sxs-lookup"><span data-stu-id="85293-149">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter.</span></span> <span data-ttu-id="85293-150">La date d’effet doit être définie comme étant l’heure d’expiration du certificat actuel (14:00:00 ou 2:00:00 PM) moins la durée de vie du jeton, dont la valeur par défaut est de huit heures.</span><span class="sxs-lookup"><span data-stu-id="85293-150">The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus token lifetime (by default eight hours).</span></span> <span data-ttu-id="85293-151">Cela nous permet de définir un moment où le certificat doit être actif et est la chaîne \<\>– EFFECTIVEDATE : « 7/22/2012 6:00:00 AM ».</span><span class="sxs-lookup"><span data-stu-id="85293-151">This gives us a time that the certificate must be set to active, and is the –EffectiveDate \<string\>: “7/22/2012 6:00:00 AM”.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="85293-152">Dans le cas d’un pool de bords, tous les certificats AudioVideoAuthentication doivent être déployés et configurés par la date et l’heure définies par le paramètre-EffectiveDate du premier certificat déployé pour éviter toute interruption de communications A/V éventuelle en raison de l’expiration du certificat en raison de la date d’expiration de ce dernier.</span><span class="sxs-lookup"><span data-stu-id="85293-152">For an Edge pool, you must have all AudioVideoAuthentication certificates deployed and provisioned by the date and time defined by the –EffectiveDate parameter of the first certificate deployed to avoid possible A/V communications disruption due to the older certificate expiring before all client and consumer tokens have been renewed using the new certificate.</span></span>

    
    </div>
    
    <span data-ttu-id="85293-153">Commande Set-CsCertificate avec les paramètres –Roll et –EffectiveTime :</span><span class="sxs-lookup"><span data-stu-id="85293-153">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="85293-154">Exemple de commande Set-CsCertificate :</span><span class="sxs-lookup"><span data-stu-id="85293-154">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="85293-p113">Le format de la date d’effet doit correspondre à celui du paramètre régional et linguistique de votre serveur. Cet exemple utilise le paramètre régional et linguistique Anglais (États-Unis)</span><span class="sxs-lookup"><span data-stu-id="85293-p113">The EffectiveDate must be formatted to match your server’s region and language settings. The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="85293-157">Une représentation chronologique constitue un moyen efficace pour mieux comprendre le processus utilisé par Set-CsCertificate, -Roll et –EffectiveDate pour créer un certificat intermédiaire permettant d’émettre de nouveaux jetons AudioVideoAuthentication tout en continuant à utiliser un certificat existant pour valider les jetons AudioVideoAuthentication en cours d’utilisation par les consommateurs.</span><span class="sxs-lookup"><span data-stu-id="85293-157">To further understand the process that Set-CsCertificate, -Roll, and –EffectiveDate use to stage a new certificate for issuing new AudioVideoAuthentication tokens while still using an existing certificate to validate AudioVideoAuthentication that are in use by consumers, a visual timeline is an effective means of understanding the process.</span></span>

<span data-ttu-id="85293-158">Dans l’exemple suivant, l’administrateur détermine que le certificat de service Edge A/V doit être échu à 2:00:00 PM sur 07/22/2012.</span><span class="sxs-lookup"><span data-stu-id="85293-158">In the following example, the administrator determines that the A/V Edge service certificate is due to expire at 2:00:00 PM on 07/22/2012.</span></span> <span data-ttu-id="85293-159">Il demande et reçoit un nouveau certificat et l’importe à chaque serveur Edge de son pool.</span><span class="sxs-lookup"><span data-stu-id="85293-159">He requests and receives a new certificate and imports it to each Edge Server in his pool.</span></span> <span data-ttu-id="85293-160">À 2 heures sur 07/22/2012, il commence à exécuter Get-CsCertificate with-roll,-empreinte égale de la chaîne d’empreintes du nouveau certificat et – EffectiveTime définie sur 07/22/2012 6:00:00 AM.</span><span class="sxs-lookup"><span data-stu-id="85293-160">At 2 AM on 07/22/2012, he begins running Get-CsCertificate with –Roll, -Thumbprint equal to the thumbprint string of the new certificate, and –EffectiveTime set to 07/22/2012 6:00:00 AM.</span></span> <span data-ttu-id="85293-161">Il exécute cette commande sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="85293-161">He runs this command on each Edge Server.</span></span>

<span data-ttu-id="85293-162">![Utilisation des paramètres Roll et EffectiveDate.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Utilisation des paramètres Roll et EffectiveDate.")</span><span class="sxs-lookup"><span data-stu-id="85293-162">![Using the Roll and the EffectiveDate parameters.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Using the Roll and the EffectiveDate parameters.")</span></span>

<span data-ttu-id="85293-163">Lorsque le temps effectif est atteint (7/22/2012 6:00:00 AM), tous les nouveaux jetons sont émis par le nouveau certificat.</span><span class="sxs-lookup"><span data-stu-id="85293-163">When the effective time is reached (7/22/2012 6:00:00 AM), all new tokens are issued by the new certificate.</span></span> <span data-ttu-id="85293-164">Lors de la validation des jetons, ces derniers sont d’abord validés par rapport au nouveau certificat.</span><span class="sxs-lookup"><span data-stu-id="85293-164">When validating tokens, tokens will first be validated against the new certificate.</span></span> <span data-ttu-id="85293-165">Si la validation échoue, l’ancien certificat est testé.</span><span class="sxs-lookup"><span data-stu-id="85293-165">If the validation fails, the old certificate is tried.</span></span> <span data-ttu-id="85293-166">La procédure de test du nouveau certificat et d’utilisation de l’ancien certificat continuera jusqu’à l’expiration de l’ancien certificat.</span><span class="sxs-lookup"><span data-stu-id="85293-166">The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate.</span></span> <span data-ttu-id="85293-167">Lorsque l’ancien certificat a expiré (7/22/2012 2:00:00 PM), les jetons sont uniquement validés par le nouveau certificat.</span><span class="sxs-lookup"><span data-stu-id="85293-167">Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate.</span></span> <span data-ttu-id="85293-168">L’ancien certificat peut être supprimé en toute sécurité à l’aide de l’applet de commande Remove-CsCertificate et du paramètre –Previous.</span><span class="sxs-lookup"><span data-stu-id="85293-168">The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="85293-169">Pour mettre à jour ou renouveler un certificat OAuthTokenIssuer à l’aide de paramètres a-roll et-EffectiveDate</span><span class="sxs-lookup"><span data-stu-id="85293-169">To update or renew an OAuthTokenIssuer certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="85293-170">Connectez-vous à l’ordinateur local en tant que membre du groupe administrateurs.</span><span class="sxs-lookup"><span data-stu-id="85293-170">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="85293-171">Demandez un renouvellement ou un nouveau certificat OAuthTokenIssuer avec la clé privée exportable pour le certificat existant sur le service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="85293-171">Request a renewal or new OAuthTokenIssuer certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="85293-172">Importez le nouveau certificat OAuthTokenIssuer sur un serveur frontal de votre pool (si vous avez déployé un pool).</span><span class="sxs-lookup"><span data-stu-id="85293-172">Import the new OAuthTokenIssuer certificate to a Front End Server in your pool (if you have a pool deployed).</span></span> <span data-ttu-id="85293-173">Le certificat OAuthTokenIssuer est répliqué globalement et ne doit être mis à jour et renouvelé que sur les serveurs de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="85293-173">The OAuthTokenIssuer certificate is replicated globally and only needs to be updated and renewed at any server in your deployment.</span></span> <span data-ttu-id="85293-174">Le serveur frontal est utilisé comme exemple.</span><span class="sxs-lookup"><span data-stu-id="85293-174">The Front End Server is used as an example.</span></span>

4.  <span data-ttu-id="85293-p117">Configurez le certificat importé avec l’applet de commande Set-CsCertificate et utilisez le paramètre –Roll avec le paramètre –EffectiveDate. La date d’effet doit être définie comme heure d’expiration du certificat actuel (14:00:00 ou 2:00:00 PM) moins 24 heures minimum.</span><span class="sxs-lookup"><span data-stu-id="85293-p117">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter. The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus a minimum of 24 hours.</span></span>
    
    <span data-ttu-id="85293-177">Commande Set-CsCertificate avec les paramètres –Roll et –EffectiveTime :</span><span class="sxs-lookup"><span data-stu-id="85293-177">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="85293-178">Exemple de commande Set-CsCertificate :</span><span class="sxs-lookup"><span data-stu-id="85293-178">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="85293-p118">Le format de la date d’effet doit correspondre à celui du paramètre régional et linguistique de votre serveur. Cet exemple utilise le paramètre régional et linguistique Anglais (États-Unis).</span><span class="sxs-lookup"><span data-stu-id="85293-p118">The EffectiveDate must be formatted to match your server’s region and language settings. The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="85293-181">Lorsque le temps effectif est atteint (7/21/2012 1:00:00 AM), tous les nouveaux jetons sont émis par le nouveau certificat.</span><span class="sxs-lookup"><span data-stu-id="85293-181">When the effective time is reached (7/21/2012 1:00:00 AM), all new tokens are issued by the new certificate.</span></span> <span data-ttu-id="85293-182">Lors de la validation des jetons, ces derniers sont d’abord validés par rapport au nouveau certificat.</span><span class="sxs-lookup"><span data-stu-id="85293-182">When validating tokens, tokens will first be validated against the new certificate.</span></span> <span data-ttu-id="85293-183">Si la validation échoue, l’ancien certificat est testé.</span><span class="sxs-lookup"><span data-stu-id="85293-183">If the validation fails, the old certificate is tried.</span></span> <span data-ttu-id="85293-184">La procédure de test du nouveau certificat et d’utilisation de l’ancien certificat continuera jusqu’à l’expiration de l’ancien certificat.</span><span class="sxs-lookup"><span data-stu-id="85293-184">The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate.</span></span> <span data-ttu-id="85293-185">Lorsque l’ancien certificat a expiré (7/22/2012 2:00:00 PM), les jetons sont uniquement validés par le nouveau certificat.</span><span class="sxs-lookup"><span data-stu-id="85293-185">Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate.</span></span> <span data-ttu-id="85293-186">L’ancien certificat peut être supprimé en toute sécurité à l’aide de l’applet de commande Remove-CsCertificate et du paramètre –Previous.</span><span class="sxs-lookup"><span data-stu-id="85293-186">The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="85293-187">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="85293-187">See Also</span></span>


[<span data-ttu-id="85293-188">Planification des certificats de serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85293-188">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="85293-189">Gestion des applications d’authentification de serveur à serveur (OAuth) et de partenaire dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85293-189">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[<span data-ttu-id="85293-190">Configuration des certificats de serveur Edge pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85293-190">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
<span data-ttu-id="85293-191">[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="85293-191">[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))</span></span>  
<span data-ttu-id="85293-192">[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="85293-192">[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

