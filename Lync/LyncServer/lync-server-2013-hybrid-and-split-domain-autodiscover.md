---
title: Hybride et domaine partagé - Découverte automatique
TOCTitle: Hybride et domaine partagé - Découverte automatique
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945652(v=OCS.15)
ms:contentKeyID: 53095525
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hybride et domaine partagé - Découverte automatique

 

_**Dernière rubrique modifiée :** 2013-02-14_

Un espace d’adressage SIP partagé, également appelé déploiement de *domaine séparé* ou déploiement *hybride*, est une configuration dans laquelle les utilisateurs sont déployés localement et dans un environnement en ligne. L’objectif est de permettre à un utilisateur, quel que soit l’emplacement de son serveur central (local ou en ligne), de se connecter au déploiement et d’être redirigé vers l’emplacement de son serveur central. La fonctionnalité de découverte automatique de Lync Server 2013 est alors utilisée pour rediriger l’utilisateur en ligne vers la topologie en ligne. Pour cela, vous devez configurer l’URL de découverte automatique à l’aide de Lync Server Management Shell et des applets de commande **Get-CsHostingProvider** et **Set-CsHostingProvider**.

## Mobilité pour le déploiement dans un domaine séparé

Vous devrez recueillir et enregistrer les attributs déployés suivants :

  - Depuis Lync Server Management Shell, tapez
    
        Get-CsHostingProvider

  - Dans les résultats, recherchez le fournisseur en ligne avec l’attribut **ProxyFQDN**. Par exemple, sipfed.online.lync.com.

  - Notez la valeur de l’attribut ProxyFQDN.

  - Activez la fédération dans le Panneau de configuration Lync Server local, ce qui autorise la fédération avec le fournisseur en ligne.

  - Activez la fédération pour le fournisseur en ligne. Par défaut, tous les utilisateurs en ligne sont activés pour la fédération de domaine et peuvent communiquer avec tous les domaines.

  - Si vous envisagez de définir des domaines bloqués et autorisés, déterminez les domaines que vous autoriserez et bloquerez de façon explicite.

  - Pour la fédération en ligne, vous devez planifier les exceptions de pare-feu, les certificats et les enregistrements d’hôtes DNS (A ou AAAA, avec IPv6). En outre, vous devez configurer les stratégies de fédération. Pour plus d’informations, voir [Planification pour la fédération de Lync Server et Office Communications Server](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)

