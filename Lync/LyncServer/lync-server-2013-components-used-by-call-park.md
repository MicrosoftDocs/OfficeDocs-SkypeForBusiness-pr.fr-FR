---
title: 'Lync Server 2013 : Composants utilisés par le parcage d’appel'
TOCTitle: Composants utilisés par le parcage d’appel
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398824(v=OCS.15)
ms:contentKeyID: 49298801
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Composants utilisés par le parcage d’appel dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-13_

L’ application de parcage d’appel est automatiquement installée quand vous déployez Voix Entreprise. Pour activer le parcage d’appel, configurez la stratégie de voix. Les composants Lync Server 2013 suivants prennent en charge l’application de parcage d’appel :

  - **service d’application**   Le service d’application fournit une plateforme pour le déploiement, l’hébergement et la gestion des applications de communications unifiées, telles que l’application de parcage d’appel. Le service d’application est installé automatiquement sur chaque serveur frontal dans un pool de serveurs frontaux et sur chaque serveur Standard Edition.

  - **application de parcage d’appel**   L’application de parcage d’appel est l’une des applications de communication unifiées hébergées par le service d’application. Il est inclus automatiquement lorsque vous déployez Voix Entreprise. Le parcage d’appel parque et récupère les appels, et gère les orbites de parcage d’appel.

  - **Fichier d’attente musicale**   Si la musique est activée, le fichier de musique est lu pendant le parcage d’un appel. Un fichier de musique par défaut est inclus quand l’application de parcage d’appel est installée.

  - **Magasin de fichiers**   L’application de parcage d’appel utilise un magasin de fichiers pour conserver les fichiers audio personnalisés.

  - **Panneau de configuration Lync Server**   Vous pouvez utiliser le Panneau de configuration Lync Server pour configurer la table d’orbites de parcage d’appel et activer le parcage d’appel pour les utilisateurs.

  - **Lync Server Management Shell**   Les applets de commande Lync Server Management Shell permettent de configurer l’application de parcage d’appel.

