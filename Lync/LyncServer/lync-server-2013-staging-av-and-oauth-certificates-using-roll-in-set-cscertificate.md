---
title: "Prép. de cert. AV et OAuth dans LS 2013 grâce à -Roll dans app. comm. Set-CsCertificate"
TOCtitle: "Prép. de cert. AV et OAuth dans LS 2013 grâce à -Roll dans app. comm. Set-CsCertificate"
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49891265
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Préparation de certificats AV et OAuth dans Lync Server 2013 à l’aide du paramètre -Roll dans l’applet de commande Set-CsCertificate

 

_**Dernière rubrique modifiée :** 2012-11-13_

Les communications audio/vidéo (A/V) constituent un composant clé de Microsoft Lync Server 2013. Les fonctionnalités telles que le partage d’applications et la conférence audio et vidéo reposent sur les certificats attribués au service Edge A/V, en particulier le service d’authentification A/V.

> [!IMPORTANT]  
> <ol>
> <li><p>Cette nouvelle fonctionnalité a été conçue pour le service Edge A/V et le certificat <em>OAuthTokenIssuer</em>. D’autres types de certificat peuvent être configurés, de même que le service Edge A/V et le type de certificat OAuth, mais ils ne bénéficieront pas du comportement de coexistence dont bénéficiera le certificat du service Edge A/V .</p></li>
> <li><p>Les applets de commande PowerShell Lync Server Management Shell utilisés pour gérer les certificats Microsoft Lync Server 2013 font référence au certificat du service Edge A/V en tant que type <em>AudioVideoAuthentication</em> et le certificat OAuthServer en tant que type <em>OAuthTokenIssuer</em>. Dans la suite de cette rubrique, les certificats seront désignés par le même type d’identificateur, <em>AudioVideoAuthentication</em> et <em>OAuthTokenIssuer</em> de manière à les identifier de manière unique.</p></li></ol>


Le service d’authentification A/V est responsable de l’émission des jetons utilisés par les clients et autres consommateurs A/V. Les jetons sont générés à partir des attributs du certificat et l’expiration de celui-ci entraîne la perte de la connexion et la nécessité de se reconnecter avec un nouveau jeton généré par le nouveau certificat. Une nouvelle fonctionnalité de Lync Server 2013 corrigera ce problème ; la possibilité de créer un nouveau certificat transitoire avant l’expiration de l’ancien certificat, et la possibilité pour les deux certificats de continuer à fonctionner pendant un certain temps. Cette fonction utilise une fonctionnalité mise à jour dans l’applet de commande Set-CsCertificate de Lync Server Management Shell. Le nouveau paramètre –Roll, avec le paramètre –EffectiveDate existant, placera le nouveau certificat AudioVideoAuthentication dans le magasin de certificats. L’ancien certificat AudioVideoAuthentication sera conservé pour permettre la validation des jetons émis. Après la mise en place du nouveau certificat AudioVideoAuthentication, la série d’événements suivante se produira :

> [!TIP]  
> L’utilisation des applets de commande Lync Server Management Shell pour gérer les certificats vous permet de demander des certificats distincts pour chaque objectif du serveur Edge. L’utilisation de l’Assistant Certificat dans l’Assistant Déploiement de Lync Server vous aide à créer des certificats, mais il s’agit généralement du type <strong>default</strong> qui regroupe toutes les utilisations de certificat du serveur Edge dans un seul certificat. La pratique recommandée si vous souhaitez utiliser la fonctionnalité de certificat propagé consiste à dissocier le certificat AudioVideoAuthentication des autres finalités du certificat. Vous pouvez configurer et créer un certificat transitoire de type Default, mais seule la partie AudioVideoAuthentication du certificat combiné bénéficiera de cette création transitoire. Par exemple, un utilisateur engagé dans une conversation de messagerie instantanée au moment de l’expiration du certificat devra se déconnecter, puis se reconnecter pour pouvoir utiliser le nouveau certificat associé au service Edge d’accès. Le même comportement se produira pour un utilisateur engagé dans une conférence web utilisant le service Edge de conférence web. Le certificat OAuthTokenIssuer est un type spécifique partagé sur tous les serveurs. Vous créez et gérez le certificat dans un emplacement et ce dernier est stocké dans le magasin central de gestion pour tous les autres serveurs.

Des informations supplémentaires sont nécessaires pour bien comprendre vos options et spécifications quand vous utilisez l’applet de commande Set-CsCertificate, notamment quand vous l’utilisez pour créer des certificats transitoires avant que le certificat actuel n’expire. Le paramètre –Roll est important, mais n’a essentiellement qu’une seule utilité. Si vous le définissez en tant que paramètre, vous indiquez à Set-CsCertificate que vous fournirez des informations sur le certificat qui sera affecté, d’après le paramètre –Type (par exemple AudioVideoAuthentication et OAuthTokenIssuer), quand le certificat entrera en vigueur selon le paramètre –EffectiveDate.

**-Roll** : le paramètre –Roll est obligatoire et comporte des dépendances également obligatoires. Paramètres requis pour définir pleinement les certificats qui seront affectés et comment ils seront appliqués :

**-EffectiveDate** : le paramètre –EffectiveDate définit à quel moment le nouveau certificat deviendra actif en même temps que le certificat actuel. Ce paramètre peut avoir une valeur proche de l’heure d’expiration du certificat actuel, ou sa valeur peut être une période plus longue. La valeur minimale recommandée du paramètre –EffectiveDate pour le certificat AudioVideoAuthentication est de 8 heures, qui est la durée de vie de jeton par défaut des jetons de service Edge A/V émis à l’aide du certificat AudioVideoAuthentication.

Lors de la création de certificats OAuthTokenIssuer transitoires, l’heure d’avance (recouvrement) doit répondre à différentes spécifications pour que le certificat puisse entrer en vigueur. Le temps d’avance minimal du certificat OAuthTokenIssuer doit être de 24 heures avant l’heure d’expiration du certificat en cours. L’heure d’avance étendue pour la coexistence est due aux autres rôles de serveur qui dépendent du certificat OAuthTokenIssuer (Exchange Server, par exemple), qui a une durée de conservation supérieure pour les clés de chiffrement et d’authentification créées à l’aide de certificats.

**-Thumbprint** : il s’agit d’un attribut figurant sur le certificat et unique pour ce certificat. Le paramètre –Thumbprint permet d’identifier le certificat qui sera affecté par les actions de l’applet de commande Set-CsCertificate.

**-Type** : Le paramètre –Type ne peut accepter qu’un seul type d’utilisation de certificat ou une liste séparée par des virgules de types d’utilisation de certificat. Les types de certificat sont ceux qui indiquent à l’applet de commande et au serveur l’utilité du certificat. Par exemple, le type AudioVideoAuthentication est destiné à être utilisé par le service Edge A/V et le service d’authentification A/V. Si vous décidez de créer un certificat transitoire et de configurer un certificat d’un autre type en même temps, vous devez prendre en considération le temps d’avance effectif minimal requis le plus long pour les certificats. Par exemple, vous devez créer des certificats transitoires de type AudioVideoAuthentication et OAuthTokenIssuer. La valeur minimale du paramètre –EffectiveDate doit être la date la plus grande des deux certificats, dans le cas présent OAuthTokenIssuer, dont le temps d’avance (recouvrement) minimal est de 24 heures. Si vous ne voulez pas créer un certificat AudioVideoAuthentication transitoire avec un temps d’avance de 24 heures, créez-le séparément avec une date d’effet supérieure à vos spécifications.

## Pour mettre à jour ou renouveler un certificat de service Edge A/V avec les paramètres –Roll et -EffectiveDate

1.  Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.

2.  Demandez le renouvellement ou un nouveau certificat AudioVideoAuthentication avec la clé privée exportable du certificat existant sur le service Edge A/V.

3.  Importez le nouveau certificat AudioVideoAuthentication vers ce serveur Edge et tout autre serveur Edge de votre pool (si vous disposez d’un pool déployé).

4.  Configurez le certificat importé à l’aide de l’applet de commande Set-CsCertificate et utilisez le paramètre –Roll avec le paramètre –EffectiveDate. La date d’effet doit être définie comme étant l’heure d’expiration du certificat actuel (14:00:00 ou 2:00:00 PM) moins la durée de vie du jeton, dont la valeur par défaut est de huit heures. Cela donne l’heure à laquelle le certificat doit être défini comme étant actif : –EffectiveDate \<string\>: “7/22/2012 6:00:00 AM”.
    
    > [!IMPORTANT]  
    > Pour un pool de serveurs Edge, tous les certificats AudioVideoAuthentication doivent être déployés et configurés pour la date et à l’heure définies par le paramètre –EffectiveDate du premier certificat déployé afin d’éviter une possible perturbation des communications A/V en raison de l’expiration du certificat le plus ancien avant que tous les jetons des clients et consommateurs aient été renouvelés à l’aide du nouveau certificat.    
    Commande Set-CsCertificate avec les paramètres –Roll et –EffectiveTime :
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Exemple de commande Set-CsCertificate :
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    > [!IMPORTANT]  
    > Le format de la date d’effet doit correspondre à celui du paramètre régional et linguistique de votre serveur. Cet exemple utilise le paramètre régional et linguistique Anglais (États-Unis)

Une représentation chronologique constitue un moyen efficace pour mieux comprendre le processus utilisé par Set-CsCertificate, -Roll et –EffectiveDate pour créer un certificat intermédiaire permettant d’émettre de nouveaux jetons AudioVideoAuthentication tout en continuant à utiliser un certificat existant pour valider les jetons AudioVideoAuthentication en cours d’utilisation par les consommateurs.

Dans l’exemple suivant, l’administrateur détermine que le certificat du service Edge A/V doit expirer à 14:00:00 le 22/07/2012. Il demande et reçoit un nouveau certificat, puis l’importe dans chaque serveur Edge de son pool. À 14:00 le 22/07/2012, il commence l’exécution de Get-CsCertificate avec le paramètre –Roll, le paramètre -Thumbprint égal à l’empreinte du nouveau certificat, et le paramètre –EffectiveTime auquel la valeur 07/22/2012 6:00:00 AM a été attribuée. Il exécute cette commande sur chaque serveur Edge.

![Utilisation des paramètres Roll et EffectiveDate.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Utilisation des paramètres Roll et EffectiveDate.")

Une fois la date d’effet atteinte (7/22/2012 6:00:00 AM), tous les nouveaux jetons sont émis par le nouveau certificat. Lors de la validation des jetons, ces derniers sont d’abord validés par rapport au nouveau certificat. Si la validation échoue, l’ancien certificat est testé. Le processus consistant à tester le nouveau certificat puis à utiliser l’ancien certificat continuera jusqu’à l’expiration de l’ancien certificat. Une fois celui-ci expiré (22/07/2012 à 14:00:00), les jetons seront uniquement validés par le nouveau certificat. L’ancien certificat peut être supprimé en toute sécurité à l’aide de l’applet de commande Remove-CsCertificate et du paramètre –Previous.

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

## Pour mettre à jour ou renouveler un certificat OAuthTokenIssuer avec les paramètres –Roll et -EffectiveDate

1.  Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.

2.  Demandez un renouvellement ou un nouveau certificat OAuthTokenIssuer avec la clé privée exportable pour le certificat existant sur le service Edge A/V.

3.  Importez le nouveau certificat dans un serveur frontal de votre pool (si vous avez déployé un pool). Le certificat OAuthTokenIssuer est répliqué globalement et ne doit être mis à jour et renouvelé que sur les serveurs de votre déploiement. Le serveur frontal est utilisé comme exemple.

4.  Configurez le certificat importé avec l’applet de commande Set-CsCertificate et utilisez le paramètre –Roll avec le paramètre –EffectiveDate. La date d’effet doit être définie comme heure d’expiration du certificat actuel (14:00:00 ou 2:00:00 PM) moins un minimum de 24 heures.
    
    Commande Set-CsCertificate avec les paramètres –Roll et –EffectiveTime :
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Exemple de commande Set-CsCertificate :
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    > [!IMPORTANT]  
    > Le format de la date d’effet doit correspondre à celui du paramètre régional et linguistique de votre serveur. Cet exemple utilise le paramètre régional et linguistique Anglais (États-Unis)

Quand la date d’effet est atteinte (7/21/2012 1:00:00 AM), tous les nouveaux jetons sont émis par le nouveau certificat. Lors de la validation des jetons, ces derniers sont d’abord validés par rapport au nouveau certificat. Si la validation échoue, l’ancien certificat est testé. Le processus consistant à tester le nouveau certificat puis à utiliser l’ancien certificat continuera jusqu’à l’expiration de l’ancien certificat. Une fois l’ancien certificat expiré (7/22/2012 2:00:00 PM), les jetons seront uniquement validés par le nouveau certificat. L’ancien certificat peut être supprimé en toute sécurité à l’aide de l’applet de commande Remove-CsCertificate et du paramètre –Previous.

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

## Voir aussi

#### Concepts

[Planification des certificats de serveur Edge dans Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Gestion de l’authentification serveur à serveur (Oauth) et des applications partenaires dans Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  

#### Autres ressources

[Configuration des certificats de serveur Edge pour Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Set-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate)  
[Remove-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCertificate)

