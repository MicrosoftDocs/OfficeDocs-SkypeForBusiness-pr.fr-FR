---
title: Configuration de la découverte automatique pour les déploiements hybrides
TOCTitle: Configuration de la découverte automatique pour les déploiements hybrides
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945653(v=OCS.15)
ms:contentKeyID: 53095527
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la découverte automatique pour les déploiements hybrides

 

_**Dernière rubrique modifiée :** 2012-12-12_

Les déploiements hybrides sont des configurations qui utilisent à la fois le déploiement local et le service sur le nuage de Microsoft Lync Online. Dans ce type de configuration, le service de découverte automatique doit être capable de localiser l’emplacement actuel de l’utilisateur. Autrement dit, le service de découverte automatique aide à trouver où se trouvent le compte d’utilisateur et le serveur hébergeant ce compte, qu’il soit dans un déploiement local ou dans le déploiement Skype Entreprise Online.

Par exemple, si un compte d’utilisateur est hébergé sur un serveur dans Skype Entreprise Online, la tentative pour le localiser se déroule en suivant un processus nommé *Détectabilité* :

  - L’utilisateur lance une tentative de connexion au déploiement local, **contoso.com**.

  - La tentative est envoyée à lyncdiscover.contoso.com, le nom DNS associé au service de découverte automatique.

  - La découverte automatique se réfère au pool de serveurs d’inscription supposé du déploiement local contoso.com et obtient des informations sur le serveur central actuel de l’utilisateur hébergé dans Skype Entreprise Online. Le service de découverte automatique envoie ensuite à l’utilisateur une référence vers le service de découverte automatique en ligne **lync.com**.

  - L’utilisateur lance une tentative de connexion vers le service de découverte automatique en ligne lync.com et peut localiser le compte et le serveur central de l’utilisateur.

Pour permettre aux clients de découvrir le déploiement dans lequel le serveur central de l’utilisateur est situé, vous devez configurer le service de découverte automatique avec une nouvelle URL. Pour configurer le service de découverte automatique, procédez comme suit :

## Configuration du service de découverte automatique pour les déploiements hybrides

1.  La rubrique [Configuration requise pour le service de découverte automatique pour Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md) propose d’utiliser Get-CsHostingProvider pour récupérer la valeur de l’attribut ProxyFQDN.

2.  Depuis Lync Server Management Shell, tapez
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    Où \[identity\] est remplacé par le nom de domaine de l’espace d’adresses SIP partagé.

## Voir aussi

#### Autres ressources

[Get-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsHostingProvider)  
[Set-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostingProvider)

