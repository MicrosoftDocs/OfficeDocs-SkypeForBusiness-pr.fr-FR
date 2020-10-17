---
title: Staging des certificats AV et OAuth à l’aide de la Set-CsCertificate
description: Staging des certificats AV et OAuth à l’aide du paramètre-Rollback dans Set-CsCertificate.
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
ms.openlocfilehash: 3732c4adb4327cc1e4111307ab2d72ed080cf221
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541840"
---
# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a>Staging des certificats AV et OAuth dans Lync Server 2013 utilisation de la Set-CsCertificate

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-13_

Les communications audio/vidéo (A/V) sont un composant clé de Microsoft Lync Server 2013. Les fonctionnalités telles que le partage d’application et la conférence audio et vidéo s’appuient sur les certificats attribués au service Edge A/V, en particulier le service d’authentification A/V.

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P>Cette nouvelle fonctionnalité est conçue pour fonctionner avec le service Edge A/V et le certificat <EM>OAuthTokenIssuer</EM> . D’autres types de certificats peuvent être mis en service avec le service Edge A/V et le type de certificat OAuth, mais ils ne bénéficieront pas du comportement de coexistence du certificat de service Edge A/V.</P>
> <LI>
> <P>Les applets de commande Lync Server Management Shell PowerShell utilisées pour gérer les certificats Microsoft Lync Server 2013 font référence au certificat de service Edge A/V comme type de certificat <EM>AudioVideoAuthentication</EM> et au certificat OAuthServer en tant que type <EM>OAuthTokenIssuer</EM>. Pour le reste de cette rubrique et pour identifier les certificats de manière unique, ils seront désignés par le même type d’identificateur, <EM>AudioVideoAuthentication</EM> et <EM>OAuthTokenIssuer</EM>.</P></LI></OL>



</div>

Le service d’authentification A/V est responsable de l’émission des jetons utilisés par les clients et autres consommateurs A/V. Les jetons sont générés à partir des attributs du certificat et l’expiration de celui-ci entraîne la perte de la connexion et la nécessité de se reconnecter avec un nouveau jeton généré par le nouveau certificat. Une nouvelle fonctionnalité de Lync Server 2013 permet d’éviter ce problème : la possibilité de mettre en place un nouveau certificat avant l’expiration de l’ancien et de faire en sorte que les deux certificats continuent de fonctionner pendant un certain temps. Cette fonctionnalité utilise la fonctionnalité mise à jour dans la cmdlet Set-CsCertificate Lync Server Management Shell. Le nouveau paramètre –Roll, avec le paramètre –EffectiveDate existant, placera le nouveau certificat AudioVideoAuthentication dans le magasin de certificats. L’ancien certificat AudioVideoAuthentication sera conservé pour permettre la validation des jetons émis. Après la mise en place du nouveau certificat AudioVideoAuthentication, la série d’événements suivante se produira :

<div>


> [!TIP]
> À l’aide des applets de commande Lync Server Management Shell pour la gestion des certificats, vous pouvez demander des certificats distincts et distincts pour chaque objectif sur le serveur Edge. L’utilisation de l’Assistant certificat dans l’Assistant Déploiement de Lync Server vous aide à créer des certificats, mais il s’agit généralement du type <STRONG>par défaut</STRONG> qui associe toutes les utilisations de certificat pour le serveur Edge à un seul certificat. La pratique recommandée si vous souhaitez utiliser la fonctionnalité de certificat propagé consiste à dissocier le certificat AudioVideoAuthentication des autres finalités du certificat. Vous pouvez configurer et créer un certificat transitoire de type Default, mais seule la partie AudioVideoAuthentication du certificat combiné bénéficiera de cette création transitoire. Un utilisateur impliqué dans (par exemple) une conversation de messagerie instantanée lorsque le certificat expire doit se déconnecter et se reconnecter pour utiliser le nouveau certificat associé au service Edge d’accès. Un comportement similaire se produira pour un utilisateur impliqué dans une conférence Web à l’aide du service Edge de conférence Web. Le certificat OAuthTokenIssuer est un type spécifique partagé sur tous les serveurs. Vous créez et gérez le certificat à un emplacement et le certificat est stocké dans le magasin central de gestion pour tous les autres serveurs.



</div>

Des informations supplémentaires sont nécessaires pour bien comprendre vos options et spécifications quand vous utilisez l’applet de commande Set-CsCertificate, notamment quand vous l’utilisez pour créer des certificats transitoires avant que le certificat actuel n’expire. Le paramètre –Roll est important, mais n’a essentiellement qu’une seule utilité. Si vous la définissez en tant que paramètre, vous indiquez Set-CsCertificate que vous allez fournir des informations sur le certificat qui sera affecté défini par – type (par exemple AudioVideoAuthentication et OAuthTokenIssuer), lorsque le certificat prendra effet défini par – EffectiveDate.

**-Roulier :** Le paramètre – ROLLBACK est obligatoire et comporte des dépendances qui doivent être fournies avec lui. Paramètres requis pour définir entièrement les certificats qui seront affectés et la façon dont ils seront appliqués :

**-EffectiveDate :** Le paramètre – EffectiveDate définit quand le nouveau certificat sera co-actif avec le certificat actuel. Le – EffectiveDate peut être proche de la date d’expiration du certificat actuel, ou il peut s’agir d’une période plus longue. Un minimum recommandé – EffectiveDate pour le certificat AudioVideoAuthentication serait de 8 heures, ce qui correspond à la durée de vie du jeton par défaut pour les jetons de service Edge AV émis à l’aide du certificat AudioVideoAuthentication.

Lors de la création de certificats OAuthTokenIssuer transitoires, l’heure d’avance (recouvrement) doit répondre à différentes spécifications pour que le certificat puisse entrer en vigueur. Le temps d’avance minimal du certificat OAuthTokenIssuer doit être de 24 heures avant l’heure d’expiration du certificat en cours. L’heure d’avance étendue pour la coexistence est due aux autres rôles de serveur qui dépendent du certificat OAuthTokenIssuer (Exchange Server, par exemple), qui a une durée de conservation supérieure pour les clés de chiffrement et d’authentification créées à l’aide de certificats.

**-Empreinte :** L’empreinte numérique est un attribut du certificat propre à ce certificat. Le paramètre – empreinte numérique est utilisé pour identifier le certificat qui sera affecté par les actions de l’applet de commande Set-CsCertificate.

**-Type :** Le paramètre – type peut accepter un seul type d’utilisation de certificat ou une liste de types d’utilisation de certificats séparés par des virgules. Les types de certificat sont ceux qui identifient l’applet de commande et le serveur en quoi consiste l’objectif du certificat. Par exemple, tapez AudioVideoAuthentication est destiné à être utilisé par le service Edge A/V et le service d’authentification antivirus. Si vous décidez d’organiser et de mettre en service des certificats d’un type différent en même temps, vous devez prendre en compte le délai d’exécution effectif minimal le plus long pour les certificats. Par exemple, vous devez organiser les certificats de type AudioVideoAuthentication et OAuthTokenIssuer. Votre minimum – EffectiveDate doit être le plus grand des deux certificats, dans ce cas l’OAuthTokenIssuer, dont le délai minimal est de 24 heures. Si vous ne souhaitez pas préparer le certificat AudioVideoAuthentication avec une période de temps de 24 heures, préparez-le séparément avec un EffectiveDate qui répond davantage à vos besoins.

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a>Pour mettre à jour ou renouveler un certificat de service Edge A/V avec les paramètres a-roulier et-EffectiveDate

1.  Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.

2.  Demandez un renouvellement ou un nouveau certificat AudioVideoAuthentication avec une clé privée exportable pour le certificat existant sur le service Edge A/V.

3.  Importez le nouveau certificat AudioVideoAuthentication sur le serveur Edge et sur tous les autres serveurs Edge de votre pool (si vous disposez d’un pool déployé).

4.  Configurez le certificat importé à l’aide de l’applet de commande Set-CsCertificate et utilisez le paramètre –Roll avec le paramètre –EffectiveDate. La date d’effet doit être définie comme étant l’heure d’expiration du certificat actuel (14:00:00 ou 2:00:00 PM) moins la durée de vie du jeton, dont la valeur par défaut est de huit heures. Cela nous donne un temps où le certificat doit être défini sur actif et est le – EffectiveDate \<string\> : « 7/22/2012 6:00:00 AM ».
    
    <div>
    

    > [!IMPORTANT]
    > Pour un pool de serveurs Edge, tous les certificats AudioVideoAuthentication doivent être déployés et configurés par la date et l’heure définies par le paramètre – EffectiveDate du premier certificat déployé afin d’éviter toute interruption possible des communications A/V en raison de l’expiration du certificat ancien avant que tous les jetons client et consommateur aient été renouvelés à l’aide du nouveau certificat.

    
    </div>
    
    Commande Set-CsCertificate avec les paramètres –Roll et –EffectiveTime :
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Exemple de commande Set-CsCertificate :
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > Le format de la date d’effet doit correspondre à celui du paramètre régional et linguistique de votre serveur. Cet exemple utilise le paramètre régional et linguistique Anglais (États-Unis)

    
    </div>

Une représentation chronologique constitue un moyen efficace pour mieux comprendre le processus utilisé par Set-CsCertificate, -Roll et –EffectiveDate pour créer un certificat intermédiaire permettant d’émettre de nouveaux jetons AudioVideoAuthentication tout en continuant à utiliser un certificat existant pour valider les jetons AudioVideoAuthentication en cours d’utilisation par les consommateurs.

Dans l’exemple suivant, l’administrateur détermine que le certificat de service Edge A/V doit expirer à 2:00:00 PM le 07/22/2012. Il demande et reçoit un nouveau certificat et l’importe sur chaque serveur Edge de son pool. À 14:00 le 22/07/2012, il commence l’exécution de Get-CsCertificate avec le paramètre –Roll, le paramètre -Thumbprint égal à l’empreinte du nouveau certificat, et le paramètre –EffectiveTime auquel la valeur 07/22/2012 6:00:00 AM a été attribuée. Il exécute cette commande sur chaque serveur Edge.

![À l’aide des paramètres rouli et EffectiveDate.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "À l’aide des paramètres rouli et EffectiveDate.")

Une fois la date d’effet atteinte (7/22/2012 6:00:00 AM), tous les nouveaux jetons sont émis par le nouveau certificat. Lors de la validation des jetons, ces derniers sont d’abord validés par rapport au nouveau certificat. Si la validation échoue, l’ancien certificat est testé. Le processus consistant à tester le nouveau certificat puis à utiliser l’ancien certificat continuera jusqu’à l’expiration de l’ancien certificat. Une fois celui-ci expiré (22/07/2012 à 14:00:00), les jetons seront uniquement validés par le nouveau certificat. L’ancien certificat peut être supprimé en toute sécurité à l’aide de l’applet de commande Remove-CsCertificate et du paramètre –Previous.

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a>Pour mettre à jour ou renouveler un certificat OAuthTokenIssuer avec les paramètres –Roll et -EffectiveDate

1.  Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.

2.  Demandez un renouvellement ou un nouveau certificat OAuthTokenIssuer avec une clé privée exportable pour le certificat existant sur le service Edge A/V.

3.  Importez le nouveau certificat OAuthTokenIssuer sur un serveur frontal de votre pool (si vous disposez d’un pool déployé). Le certificat OAuthTokenIssuer est répliqué globalement et ne doit être mis à jour et renouvelé que sur les serveurs de votre déploiement. Le serveur frontal est utilisé à titre d’exemple.

4.  Configurez le certificat importé avec l’applet de commande Set-CsCertificate et utilisez le paramètre –Roll avec le paramètre –EffectiveDate. La date d’effet doit être définie comme heure d’expiration du certificat actuel (14:00:00 ou 2:00:00 PM) moins un minimum de 24 heures.
    
    Commande Set-CsCertificate avec les paramètres –Roll et –EffectiveTime :
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Exemple de commande Set-CsCertificate :
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > Le format de la date d’effet doit correspondre à celui du paramètre régional et linguistique de votre serveur. Cet exemple utilise le paramètre régional et linguistique Anglais (États-Unis)

    
    </div>

Quand la date d’effet est atteinte (7/21/2012 1:00:00 AM), tous les nouveaux jetons sont émis par le nouveau certificat. Lors de la validation des jetons, ces derniers sont d’abord validés par rapport au nouveau certificat. Si la validation échoue, l’ancien certificat est testé. Le processus consistant à tester le nouveau certificat puis à utiliser l’ancien certificat continuera jusqu’à l’expiration de l’ancien certificat. Une fois l’ancien certificat expiré (7/22/2012 2:00:00 PM), les jetons seront uniquement validés par le nouveau certificat. L’ancien certificat peut être supprimé en toute sécurité à l’aide de l’applet de commande Remove-CsCertificate et du paramètre –Previous.

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification des certificats de serveur Edge dans Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Gestion de l’authentification de serveur à serveur (OAuth) et des applications partenaires dans Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[Configurer des certificats de serveur Edge pour Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))  
[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

