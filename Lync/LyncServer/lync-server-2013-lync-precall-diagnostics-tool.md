---
title: 'Lync Server 2013 : outil de diagnostic de préappel Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0377460340e1b639a7fca5862dcd85aed399b94a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a>Outil de diagnostic de préappel Lync dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-11-04_

L’outil Lync precall Diagnostics (PCD) est une application cliente qui vous permet de voir comment l’état actuel de votre réseau peut avoir un impact sur la qualité audio dans un appel vocal à venir.

PCD est très utile dans les situations où le dernier tronçon d’un réseau est probablement le plus faible (par exemple, avec des ordinateurs portables sur un réseau WiFi public ou des particuliers). PCD crée un petit flux de paquets qui traverse cette branche finale du réseau. L’outil analyse ensuite le flux de paquets pour estimer comment la gigue et la perte le long de cette jambe peuvent influer sur la qualité de l’appel, puis fournit un rapport. Vous pouvez exécuter PCD en continu sur le client, même lorsque des appels sont en cours. Le flux de paquets n’a pas d’impact significatif sur la bande passante.

**La dernière version du PCD, version 1,1, inclut les améliorations suivantes :**

  - Prendre en charge des mots de passe plus longs, qui peuvent désormais contenir jusqu’à 127 caractères

  - Diagnostics supplémentaires pour les problèmes de connexion à l’authentification

  - Meilleure prise en charge des déploiements hybrides Lync

  - Mises à jour du sélecteur d’informations d’identification

  - Améliorations de la stabilité

Nous apprécions tout commentaire. Veuillez envoyer toutes les questions d’assistance ou tous les problèmes à l' <pcdfb@microsoft.com>alias de [Commentaire PCD](mailto:pcdfb@microsoft.com) à l’adresse.

Cette rubrique comprend les sections suivantes :

  - Versions de Lync PCD

  - Configuration requise pour Lync PCD

  - Fonctionnalités de Lync PCD

  - Exécution de Lync PCD

  - Désinstallation de Lync PCD

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a>Versions de Lync PCD

Cette rubrique décrit les versions suivantes de l’outil, disponibles en téléchargement gratuit :

  - Application de bureau Windows[https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914)()

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a>Configuration requise pour Lync PCD

<div>


> [!NOTE]  
> PCD nécessite l’installation et la configuration de l’API Web Unified Communications (UCWA) pour prendre en charge les clients mobiles dans le déploiement Lync Server. UCWA est installé avec Lync Server.



</div>

<div>

## <a name="windows-desktop-app-requirements"></a>Configuration requise pour les applications de bureau Windows

  - N’importe quelle édition du système d’exploitation Windows 7 ou Windows 8

  - Microsoft .NET Framework 4,5 disponible sur[https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a>Fonctionnalités de Lync PCD

Lync PCD inclut les fonctionnalités suivantes :

  - Exécution par défaut à la demande (rafales de 2 minutes)

  - Mode de fonctionnement toujours activé (jusqu’à 24 heures en mode alignement)

  - Vue historique de vos séries de tests

  - Diagnostiquer les échecs de connexion (Lync PCD pour Windows 8 uniquement)

![Capture d’écran de connexion des fonctionnalités Lync PCD](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Capture d’écran de connexion des fonctionnalités Lync PCD")

  - Vue graphique des mesures réseau : MOS réseau, perte de paquets et gigue d’interarrivée en mode plein écran et en mode d’affichage ancré.

**Affichage plein écran**

![Graphiques de résultats de test de l’outil de diagnostic d’avant-appel](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Graphiques de résultats de test de l’outil de diagnostic d’avant-appel")

**Vue aimantée**

![Résultats du test d’utilisation de l’outil de diagnostic d’avant-appel](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Résultats du test d’utilisation de l’outil de diagnostic d’avant-appel")

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a>Exécution de Lync PCD

<div>

## <a name="running-windows-desktop-app"></a>Exécution de l’application de bureau Windows

1.  Pour démarrer le PCD sur un système Windows 7, sélectionnez **Précall Diagnostics** dans le menu **Démarrer** .
    
    Pour démarrer le PCD sur un système Windows 8, sélectionnez l’icône sur votre écran de démarrage, ou recherchez « préappels Diagnostics ».
    
    ![Icône de l’outil de diagnostic d’avant-appel](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Icône de l’outil de diagnostic d’avant-appel")

2.  Lorsque l’outil démarre, sélectionnez la méthode de votre choix pour fournir les informations d’identification et sélectionnez le mode de fonctionnement réseau dans la boîte de dialogue Options de l' **outil de diagnostic** de l’avant-appel, puis cliquez sur **OK**:

3.  Sélectionnez le bouton **Démarrer le test** pour commencer à exécuter les Diagnostics.
    
    Si vous avez sélectionné l’option **utiliser les informations d’identification réseau** , le test commence immédiatement.
    
    Si vous avez sélectionné l’option **me laisser entrer des informations d’identification** , la boîte de dialogue **sécurité de Windows** s’ouvre. Une fois que vous avez entré vos informations d’identification, le test démarre.

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a>Désinstallation de Lync PCD

Pour supprimer Lync PCD, suivez la procédure correspondant à votre système d’exploitation :

  - Sur un système Windows 7, ouvrez le **panneau de configuration**, sélectionnez **programmes et fonctionnalités**, puis double-cliquez sur **Lync 2013 precall Diagnostics**.

  - Sur un système Windows 8, cliquez avec le bouton droit sur la vignette PCD, puis cliquez sur **désinstaller** dans la barre de l’application en bas de l’écran d’accueil.

</div>

</div>

<span> </span>

</div>

</div>

</div>

