---
title: Vérification de la coexistence du pool pilote avec le pool hérité
TOCTitle: Vérification de la coexistence du pool pilote avec le pool hérité
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205420(v=OCS.15)
ms:contentKeyID: 49299465
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vérification de la coexistence du pool pilote avec le pool hérité

 

_**Dernière rubrique modifiée :** 2012-09-29_

Après avoir déployé le premier pool, vous devez vérifier la coexistence des deux pools à l’aide des outils d’administration pour afficher les informations des pools. Pour les pools Lync Server 2013 et les pools hérités, vous devez utiliser les outils Panneau de configuration Lync Server 2013 et générateur de topologie.

## Vérification du démarrage des services Lync Server 2013

1.  Depuis le serveur frontal Lync Server 2013, accédez à Outils d’administration\\Applet Services.

2.  Vérifiez que les services suivants sont exécutés sur le serveur frontal :

**Services Lync Server 2013**

![Liste des services Lync Server démarrés](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "Liste des services Lync Server démarrés")

## Ouverture du Panneau de configuration Lync Server 2013

Depuis le serveur frontal de votre déploiement Lync Server 2013, ouvrez le Panneau de configuration Lync Server 2013 et sélectionnez le pool Lync Server 2010. Répétez la procédure pour ouvrir le pool Lync Server 2013.

**Ouvrez le Panneau de configuration Lync Server 2013.**

![Boîte de dialogue de sélection d’URL](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Boîte de dialogue de sélection d’URL")

> [!IMPORTANT]  
> Sur Lync Server 2013, vous devez mettre à niveau Silverlight vers Silverlight 5 avant d’utiliser le Panneau de configuration Lync Server.

Cette topologie inclut à présent les rôles serveur Lync Server 2010 et Lync Server 2013.

**Page Topologie du Panneau de configuration Lync Server 2013**

![Page Topologie du panneau de configuration de Lync Server](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Page Topologie du panneau de configuration de Lync Server")

## Ne pas essayer d’ouvrir la topologie dans le générateur de topologie Lync Server 2010

Si vous essayez d’ouvrir la topologie en utilisant le générateur de topologie Lync Server 2010, le message d’erreur ci-dessous s’affichera. La topologie peut uniquement être affichée en utilisant le générateur de topologie Lync Server 2013. Le générateur de topologie Lync Server 2013 doit être utilisé pour créer des pools pour Lync Server 2013 et Lync Server 2010.

**Message d’erreur du générateur de topologie Lync Server 2010**

![Erreur du composant logiciel enfichable MMC du Générateur de topologie Lync Server](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Erreur du composant logiciel enfichable MMC du Générateur de topologie Lync Server")

