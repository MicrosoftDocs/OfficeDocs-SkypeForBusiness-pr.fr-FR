---
title: "Lync Server 2013 : Conf. de la déc. auto pr la mob. ac les dépl. hybrides"
TOCTitle: Configuration de la découverte automatique pour la mobilité avec les déploiements hybrides
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ215885(v=OCS.15)
ms:contentKeyID: 49299384
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la découverte automatique dans Lync Server 2013 pour la mobilité avec les déploiements hybrides

 

_**Dernière rubrique modifiée :** 2014-06-18_

Les déploiements hybrides sont des configurations qui utilisent à la fois le déploiement local et le service sur le nuage de Microsoft Lync Online. Dans ce type de configuration, le service de découverte automatique doit être capable de rechercher l’emplacement actuel de l’utilisateur. C’est à dire que le service de découverte automatique aide à trouver où le compte d’utilisateur et le serveur hébergeant ce compte sont situés, qu’il soit dans un déploiement local ou dans un déploiement Skype Entreprise Online.

Par exemple, si un compte d’utilisateur est hébergé sur un serveur dans Skype Entreprise Online, la tentative pour le rechercher se déroule en suivant un processus nommé *Détectabilité*  :

  - L’utilisateur lance une tentative de connexion au déploiement local, **contoso.com**.

  - La tentative est envoyée à lyncdiscover.contoso.com, le nom de DNS associé au service de découverte automatique.

  - La découverte automatique se réfère au pool de serveurs d’inscription supposé du déploiement local contoso.com et obtient des informations sur le serveur central actuel de l’utilisateur hébergé dans Skype Entreprise Online. Le service de découverte automatique envoie ensuite à l’utilisateur une référence vers le service de découverte automatique en ligne **lync.com**.

  - L’utilisateur lance une tentative de connexion vers le service de découverte automatique en ligne lync.com et peut rechercher le compte et le serveur central de l’utilisateur.

Pour permettre aux clients mobiles de découvrir le déploiement dans lequel le serveur d’hébergement de l’utilisateur est situé, vous devez configurer le service de découverte automatique avec une nouvelle URL. Pour configurer le service de découverte automatique, procédez comme suit :

## Configuration de la découverte automatique pour les déploiements hybrides

1.  Vous utilisez Get-CsHostingProvider pour récupérer la valeur de l’attribut ProxyFQDN.

2.  Depuis Lync Server Management Shell, tapez
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    Où \[identity\] est remplacé par le nom de domaine de l’espace d’adresses SIP partagé.

## Voir aussi

#### Autres ressources

[Get-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsHostingProvider)  
[Set-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostingProvider)

