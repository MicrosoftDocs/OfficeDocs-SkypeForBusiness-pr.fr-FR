---
title: Scénario de migration standard - Haut niveau
TOCTitle: Scénario de migration standard - Haut niveau
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205354(v=OCS.15)
ms:contentKeyID: 49299182
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Scénario de migration standard - Haut niveau

 

_**Dernière rubrique modifiée :** 2013-01-30_

Les éléments suivants vous servent de point de départ lorsque vous migrez un Lync Server 2010, conversation de groupe ou Group ChatOffice Communications Server 2007 R2 vers un serveur de conversations permanentesLync Server 2013. Le chemin de la migration de Lync Server 2013 standard est le suivant :

  - Votre entreprise a déployé un Lync Server 2010, conversation de groupe or Group ChatOffice Communications Server 2007 R2 précédemment, et vous voulez déployer serveur de conversations permanentesLync Server 2013.

  - Déployez Lync Server 2013, puis déployez le (ou les) pool de serveurs de conversations permanentes.

  - Préparez et planifiez la migration de vos salles de conversation permanente, puis déterminez une heure appropriée pour fermer le système pour la migration.

  - Exécutez les applets de commande Windows PowerShell à des fins de migration (**Export-CsPersistentChatData** et **Import-CsPersistentChatData**) pour déplacer le contenu vers serveur de conversations permanentes.

  - Vérifiez que la migration a réussi.

  - Désactivez votre déploiement hérité.

  - Configurez le serveur de conversations permanentes de sorte que les clients hérités puissent se connecter au serveur de conversations permanentesLync Server 2013. Cette action est nécessaire, car le déploiement de nouveaux clients prend du temps, et les utilisateurs existants avec des clients hérités doivent avoir accès à leurs salles de conversation dès que possible.

  - Déployez de nouveaux clients, tout en continuant à vous assurer que les utilisateurs avec des Group Chat (clients) hérités peuvent accéder à leurs salles de conversation.

