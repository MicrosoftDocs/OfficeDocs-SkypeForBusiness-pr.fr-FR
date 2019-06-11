---
title: 'Lync Server 2013: outil Diagnostics pour les préappel Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e22b542a5840714455d4abdb0a7163e6a8ba748
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a>Outil de diagnostics d’préappel Lync dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2016-11-04_

L’outil de diagnostics d’avant-appel Lync (PCD) est une application basée sur le client qui vous permet de voir comment l’état actuel de votre réseau peut avoir un impact sur la qualité audio lors d’un appel voix entreprise à venir.

PCD est particulièrement utile dans les situations dans lesquelles le dernier tronçon d’un réseau est susceptible d’être faible (par exemple, avec des ordinateurs portables sur un réseau WiFi public ou des particuliers). PCD crée un petit flux de paquets qui traverse ce dernier tronçon du réseau. L’outil analyse alors le flux de paquets pour évaluer la façon dont la gigue et la perte peuvent avoir un impact sur la qualité des appels, puis fournit un rapport. Vous pouvez exécuter PCD en continu sur le client, même lorsque les appels sont en train d’être placés. Le flux de paquets n’a pas d’effet notable sur la bande passante.

**La dernière version du PCD, version 1,1, inclut les améliorations suivantes:**

  - Prise en charge de mots de passe plus longs, qui peuvent désormais comporter jusqu’à 127 caractères

  - Diagnostics supplémentaires pour les problèmes de connexion d’authentification

  - Prise en charge améliorée des déploiements hybrides de Lync

  - Mises à jour du sélecteur d’informations d’identification

  - Améliorations de la stabilité

Nous vous remercions de votre avis. Vous pouvez envoyer toutes vos questions ou problèmes d’assistance à l’alias <pcdfb@microsoft.com>de [Commentaires PCD](mailto:pcdfb@microsoft.com) à l’adresse.

Cette rubrique inclut les sections suivantes :

  - Versions de Lync PCD

  - Configuration système requise pour Lync PCD

  - Fonctionnalités de Lync PCD

  - Exécution de Lync PCD

  - Désinstallation de Lync PCD

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a>Versions de Lync PCD

Cette rubrique décrit les versions suivantes de l’outil disponibles en téléchargement gratuit:

  - Application de bureau Windows[http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914)()

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a>Configuration système requise pour Lync PCD

<div>


> [!NOTE]  
> PCD nécessite l’installation et la configuration de l’API Web de communications unifiées (UCWA) pour la prise en charge des clients mobiles dans le déploiement de Lync Server. UCWA est installé avec Lync Server.



</div>

<div>

## <a name="windows-desktop-app-requirements"></a>Configuration requise pour l’application de bureau Windows

  - Toute édition du système d’exploitation Windows 7 ou Windows 8

  - Microsoft .NET Framework 4,5 disponible sur le[http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a>Fonctionnalités de Lync PCD

Lync PCD inclut les fonctionnalités suivantes:

  - Exécution par défaut à la demande (burst de 2 minutes)

  - Exécution dans le mode toujours activé (jusqu’à 24 heures dans l’affichage aligné)

  - Affichage historique de vos séries de tests

  - Diagnostiquer les échecs de connexion (Lync PCD pour Windows 8 uniquement)

![Capture d’écran de la capture d’écran de l’application Lync] (images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Capture d’écran de la capture d’écran de l’application Lync")

  - Affichage graphique des métriques du réseau (MOS du réseau, perte de paquets et gigue d’interentrée) en plein écran et en affichage aligné.

**Mode plein écran**

Graphes de résultats de test de l' ![outil de diagnostic avant appel] Graphes de résultats de test de l' (images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "outil de diagnostic avant appel")

**Affichage aligné**

![Résultats du test d’utilisation de l’outil de diagnostic avant appel] (images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Résultats du test d’utilisation de l’outil de diagnostic avant appel")

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a>Exécution de Lync PCD

<div>

## <a name="running-windows-desktop-app"></a>Exécution d’une application de bureau Windows

1.  Pour démarrer le PCD sur un système Windows 7, sélectionnez **Diagnostics préappel** dans le menu **Démarrer** .
    
    Pour démarrer le PCD sur un système Windows 8, sélectionnez l’icône sur votre écran d’accueil, ou recherchez «Diagnostics de préappel».
    
    ![Icône] de l’outil de diagnostic préappel (images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Icône") de l’outil de diagnostic préappel

2.  Lorsque l’outil démarre, sélectionnez la méthode de votre choix pour fournir des informations d’identification, puis sélectionnez le mode de fonctionnement réseau dans la boîte de dialogue Options de l' **outil Diagnostics** de l’appel, puis cliquez sur **OK**:

3.  Cliquez sur le bouton **Démarrer le test** pour démarrer l’exécution des Diagnostics.
    
    Si vous avez sélectionné l’option **utiliser les informations d’identification réseau** , le test commence immédiatement.
    
    Si vous avez sélectionné l’option **me permettre d’entrer mes informations d’identification** , la boîte de dialogue de **sécurité Windows** s’ouvre. Après avoir entré vos informations d’identification, le test démarre.

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a>Désinstallation de Lync PCD

Pour supprimer Lync PCD, suivez la procédure pour votre système d’exploitation:

  - Sur un système Windows 7, ouvrez le **panneau de configuration**, sélectionnez **programmes et fonctionnalités**, puis double-cliquez sur Diagnostics de l' **appel Lync 2013**.

  - Sur un système Windows 8, cliquez avec le bouton droit sur la vignette PCD **** , puis cliquez sur désinstaller dans la barre de l’application en bas de l’écran d’accueil.

</div>

</div>

<span> </span>

</div>

</div>

</div>

