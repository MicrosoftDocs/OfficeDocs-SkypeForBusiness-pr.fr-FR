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

# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a>Test de l’audiovisuel et des certificats OAuth dans Lync Server 2013 à l’aide du CsCertificate

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-13_

Les communications audio/vidéo (A/V) sont un composant clé de Microsoft Lync Server 2013. Les fonctionnalités telles que le partage d’application et les conférences audio et vidéo sont basées sur les certificats attribués au service Edge A/V, en particulier le service d’authentification A/V.

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P>Cette nouvelle fonctionnalité est conçue pour fonctionner pour le service Edge A/V et le certificat <EM>OAuthTokenIssuer</EM> . D’autres types de certificats peuvent être configurés avec le service Edge A/V et le type de certificat OAuth, mais ils ne pourront pas bénéficier du comportement de coexistence du certificat de service Edge A/V.</P>
> <LI>
> <P>Les applets de certification PowerShell Lync Server Management Shell utilisées pour gérer les certificats Microsoft Lync Server 2013 font référence au certificat de service A/V, comme le type de certificat <EM>AudioVideoAuthentication</EM> et au certificat OAuthServer en tant que type <EM>OAuthTokenIssuer</EM>. Dans la suite de cette rubrique, les certificats seront désignés par le même type d’identificateur, <EM>AudioVideoAuthentication</EM> et <EM>OAuthTokenIssuer</EM> de manière à les identifier de manière unique.</P></LI></OL>



</div>

Le service d’authentification A/V est responsable de l’émission des jetons utilisés par les clients et autres consommateurs A/V. Les jetons sont générés à partir des attributs du certificat et l’expiration du certificat entraîne la perte de la connexion et la nécessité de se reconnecter avec un nouveau jeton généré par le nouveau certificat. Pour résoudre ce problème, une nouvelle fonctionnalité de Lync Server 2013 résout le problème : la possibilité de mettre à niveau un nouveau certificat à l’avance de l’ancien et de laisser fonctionner les deux certificats pour une période donnée. Cette fonctionnalité utilise des fonctionnalités mises à jour dans la cmdlet Set-CsCertificate Lync Server Management Shell. Le nouveau paramètre –Roll, avec le paramètre –EffectiveDate existant, placera le nouveau certificat AudioVideoAuthentication dans le magasin de certificats. L’ancien certificat AudioVideoAuthentication sera conservé pour permettre la validation des jetons émis. Après la mise en place du nouveau certificat AudioVideoAuthentication, la série d’événements suivante se produira :

<div>


> [!TIP]
> À l’aide des applets de certification Lync Server Management Shell pour la gestion des certificats, vous pouvez demander des certificats distincts et distincts à chaque objectif sur le serveur Edge. L’Assistant Création de certificat de l’Assistant Déploiement de Lync Server vous aide à créer des certificats, mais il s’agit généralement du type <STRONG>par défaut</STRONG> qui combine l’ensemble des certificats pour le serveur de périphérie sur un certificat unique. Si vous souhaitez utiliser la fonctionnalité de certificat propagé, la pratique recommandée consiste à dissocier le certificat AudioVideoAuthentication des autres finalités du certificat. Vous pouvez configurer et créer un certificat transitoire de type Default, mais seule la partie AudioVideoAuthentication du certificat combiné bénéficiera de cette création transitoire. Un utilisateur impliqué dans une conversation de messagerie instantanée alors qu’il expire doit se déconnecter puis se reconnecter pour pouvoir utiliser le nouveau certificat associé au service Edge d’accès. Un comportement similaire sera observé pour un utilisateur impliqué dans une conférence Web à l’aide du service Edge de conférence Web. Le certificat OAuthTokenIssuer est un type spécifique partagé sur tous les serveurs. Vous créez et gérez le certificat à un emplacement unique et le certificat est stocké dans le magasin de gestion central pour tous les autres serveurs.



</div>

Des informations supplémentaires sont nécessaires pour bien comprendre vos options et spécifications quand vous utilisez l’applet de commande Set-CsCertificate, par exemple, lorsque vous l’utilisez pour créer des certificats transitoires avant que le certificat actuel expire. Le paramètre –Roll est important, mais n’a, en substance, qu’une seule utilité. Si vous le définissez sous forme de paramètre, vous indiquez à Set-CsCertificate que vous fournirez des informations sur le certificat qui sera affecté, d’après le paramètre –Type (par exemple, AudioVideoAuthentication et OAuthTokenIssuer), quand le certificat entrera en vigueur selon le paramètre –EffectiveDate.

**-Roll :** Le paramètre – Roll est obligatoire et dispose de dépendances qui doivent être fournies conjointement. Paramètres requis pour définir entièrement les certificats qui seront touchés et la manière dont ils sont appliqués :

**-EffectiveDate :** Le paramètre – EffectiveDate définit le moment où le nouveau certificat devient coactif avec le certificat actuel. Le – EffectiveDate peut être proche de la date d’expiration du certificat actuel ou bien il peut s’agir d’une période de temps plus longue. Une valeur minimale recommandée – EffectiveDate pour le certificat AudioVideoAuthentication serait de 8 heures, qui correspond à la durée de vie du jeton par défaut pour les jetons de service Edge AV émis à l’aide du certificat AudioVideoAuthentication.

Lors de la création de certificats OAuthTokenIssuer transitoires, l’heure d’avance (recouvrement) doit répondre à différentes spécifications pour que le certificat puisse entrer en vigueur. Le temps d’avance minimal du certificat OAuthTokenIssuer doit être de 24 heures avant l’heure d’expiration du certificat en cours. L’heure d’avance étendue pour la coexistence est due aux autres rôles de serveur qui dépendent du certificat OAuthTokenIssuer (Exchange Server, par exemple), qui possède une durée de conservation supérieure pour les clés de chiffrement et d’authentification créées à l’aide de certificats.

**-Empreinte numérique :** L’empreinte numérique est un attribut du certificat unique de ce certificat. Le paramètre-d’empreinte numérique est utilisé pour identifier le certificat qui sera affecté par les actions de l’applet de certification Set-CsCertificate.

**-Type :** Le paramètre – type peut accepter un type d’utilisation de certificat unique ou une liste séparée par des virgules des types d’utilisation de certificats. Les types de certificats sont ceux qui identifient l’objet du certificat sur l’applet de certification et sur le serveur. Par exemple, tapez AudioVideoAuthentication doit être utilisé par le service Edge A/V et le service d’authentification AV. Si vous décidez de mettre en place des certificats d’un type différent en même temps, vous devez prendre en considération le délai d’exécution effectif le plus long requis pour les certificats. Par exemple, vous devez organiser des certificats de type AudioVideoAuthentication et OAuthTokenIssuer. Le minimum-EffectiveDate doit être le plus important des deux certificats, dans le cas présent OAuthTokenIssuer, dont le délai de 24 heures est minimal. Si vous ne souhaitez pas organiser le certificat AudioVideoAuthentication avec un délai de 24 heures, emphasez-le séparément avec un EffectiveDate qui répond à vos besoins.

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a>Pour mettre à jour ou renouveler un certificat de service Edge A/V à l’aide de paramètres a-roll et EffectiveDate

1.  Connectez-vous à l’ordinateur local en tant que membre du groupe administrateurs.

2.  Demandez un renouvellement ou un nouveau certificat AudioVideoAuthentication avec la clé privée exportable pour le certificat existant sur le service Edge A/V.

3.  Importez le nouveau certificat AudioVideoAuthentication sur le serveur Edge et sur tous les autres serveurs Edge de votre pool (si vous avez déployé un pool).

4.  Configurez le certificat importé à l’aide de l’applet de commande Set-CsCertificate et utilisez le paramètre –Roll avec le paramètre –EffectiveDate. La date d’effet doit être définie comme étant l’heure d’expiration du certificat actuel (14:00:00 ou 2:00:00 PM) moins la durée de vie du jeton, dont la valeur par défaut est de huit heures. Cela nous permet de définir un moment où le certificat doit être actif et est la chaîne \<\>– EFFECTIVEDATE : « 7/22/2012 6:00:00 AM ».
    
    <div>
    

    > [!IMPORTANT]
    > Dans le cas d’un pool de bords, tous les certificats AudioVideoAuthentication doivent être déployés et configurés par la date et l’heure définies par le paramètre-EffectiveDate du premier certificat déployé pour éviter toute interruption de communications A/V éventuelle en raison de l’expiration du certificat en raison de la date d’expiration de ce dernier.

    
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

Dans l’exemple suivant, l’administrateur détermine que le certificat de service Edge A/V doit être échu à 2:00:00 PM sur 07/22/2012. Il demande et reçoit un nouveau certificat et l’importe à chaque serveur Edge de son pool. À 2 heures sur 07/22/2012, il commence à exécuter Get-CsCertificate with-roll,-empreinte égale de la chaîne d’empreintes du nouveau certificat et – EffectiveTime définie sur 07/22/2012 6:00:00 AM. Il exécute cette commande sur chaque serveur Edge.

![Utilisation des paramètres Roll et EffectiveDate.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Utilisation des paramètres Roll et EffectiveDate.")

Lorsque le temps effectif est atteint (7/22/2012 6:00:00 AM), tous les nouveaux jetons sont émis par le nouveau certificat. Lors de la validation des jetons, ces derniers sont d’abord validés par rapport au nouveau certificat. Si la validation échoue, l’ancien certificat est testé. La procédure de test du nouveau certificat et d’utilisation de l’ancien certificat continuera jusqu’à l’expiration de l’ancien certificat. Lorsque l’ancien certificat a expiré (7/22/2012 2:00:00 PM), les jetons sont uniquement validés par le nouveau certificat. L’ancien certificat peut être supprimé en toute sécurité à l’aide de l’applet de commande Remove-CsCertificate et du paramètre –Previous.

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a>Pour mettre à jour ou renouveler un certificat OAuthTokenIssuer à l’aide de paramètres a-roll et-EffectiveDate

1.  Connectez-vous à l’ordinateur local en tant que membre du groupe administrateurs.

2.  Demandez un renouvellement ou un nouveau certificat OAuthTokenIssuer avec la clé privée exportable pour le certificat existant sur le service Edge A/V.

3.  Importez le nouveau certificat OAuthTokenIssuer sur un serveur frontal de votre pool (si vous avez déployé un pool). Le certificat OAuthTokenIssuer est répliqué globalement et ne doit être mis à jour et renouvelé que sur les serveurs de votre déploiement. Le serveur frontal est utilisé comme exemple.

4.  Configurez le certificat importé avec l’applet de commande Set-CsCertificate et utilisez le paramètre –Roll avec le paramètre –EffectiveDate. La date d’effet doit être définie comme heure d’expiration du certificat actuel (14:00:00 ou 2:00:00 PM) moins 24 heures minimum.
    
    Commande Set-CsCertificate avec les paramètres –Roll et –EffectiveTime :
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Exemple de commande Set-CsCertificate :
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > Le format de la date d’effet doit correspondre à celui du paramètre régional et linguistique de votre serveur. Cet exemple utilise le paramètre régional et linguistique Anglais (États-Unis).

    
    </div>

Lorsque le temps effectif est atteint (7/21/2012 1:00:00 AM), tous les nouveaux jetons sont émis par le nouveau certificat. Lors de la validation des jetons, ces derniers sont d’abord validés par rapport au nouveau certificat. Si la validation échoue, l’ancien certificat est testé. La procédure de test du nouveau certificat et d’utilisation de l’ancien certificat continuera jusqu’à l’expiration de l’ancien certificat. Lorsque l’ancien certificat a expiré (7/22/2012 2:00:00 PM), les jetons sont uniquement validés par le nouveau certificat. L’ancien certificat peut être supprimé en toute sécurité à l’aide de l’applet de commande Remove-CsCertificate et du paramètre –Previous.

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification des certificats de serveur Edge dans Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Gestion des applications d’authentification de serveur à serveur (OAuth) et de partenaire dans Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[Configuration des certificats de serveur Edge pour Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))  
[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

