---
title: 'Lync Server 2013 : Vérification de la conception de la topologie'
TOCTitle: Vérification de la conception de la topologie
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412951(v=OCS.15)
ms:contentKeyID: 49298729
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vérification de la conception de la topologie dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-01-02_

Le Générateur de topologie vérifie automatiquement la topologie. Toute erreur de topologie est identifiée en tant qu’erreur de validation et signalée par l’icône d’erreur de validation en regard du rôle serveur. Il est également important de vérifier que la topologie représente correctement la topologie du déploiement.

## Pour vérifier la topologie avant la publication

1.  Vérifiez que toutes les URL simples sont configurées correctement.

2.  Confirmez que le serveur SQL Server est en ligne et que l’ordinateur sur lequel le Générateur de topologie est installé peut y accéder. Confirmez également que les règles de pare-feu nécessaires sont disponibles.

3.  Confirmez que le partage de fichiers est disponible et qu’il dispose des autorisations appropriées qui ont été définies.

4.  Confirmez que les rôles serveur corrects qui répondent à la configuration requise pour le déploiement sont définis dans la topologie.

5.  Vérifiez que les serveurs existent dans les services de domaine Active Directory. Cela se produit automatiquement si vous avez joint les serveurs au domaine.

Lorsque vous avez vérifié la topologie et qu’aucune erreur de validation n’a été détectée, vous êtes prêt à publier la topologie. Si des erreurs de validation sont détectées, vous devez les corriger pour pouvoir publier la topologie. Pour plus d’informations sur la publication de votre topologie, reportez-vous à [Publication de la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md).

