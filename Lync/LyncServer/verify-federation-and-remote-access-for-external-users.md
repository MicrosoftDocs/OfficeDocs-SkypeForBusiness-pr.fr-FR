---
title: Vérification de la fédération et de l’accès distant des utilisateurs externes
TOCTitle: Vérification de la fédération et de l’accès distant des utilisateurs externes
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49891474
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vérification de la fédération et de l’accès distant des utilisateurs externes

 

_**Dernière rubrique modifiée :** 2012-09-18_

Après avoir effectué la transition de l’itinéraire de fédération vers le serveur EdgeLync Server 2013, vous devez effectuer des tests fonctionnels pour vous assurer que la fédération se comporte comme prévu. Les tests relatifs à l’accès des utilisateurs externes doivent inclure chaque type d’utilisateur externe pris en charge par votre organisation, notamment une partie ou l’ensemble de ce qui suit.

## Tester la connectivité des utilisateurs externes et de l’accès externe

  - Utilisateurs d’au moins un domaine fédéré, un utilisateur interne sur Lync Server 2013 et un utilisateur sur Lync Server 2010. Testez la messagerie instantanée, la présence, l’audio/vidéo (A/V) et le partage de Bureau.

  - Utilisateurs de chaque fournisseur de service de messagerie instantanée public que votre entreprise prend en charge (et dont la configuration a été effectuée) en communiquant avec un utilisateur sur Lync Server 2013 et un utilisateur sur Lync Server 2010.

  - Vérifiez que les utilisateurs anonymes peuvent participer à des conférences.

  - Utilisateur hébergé sur Lync Server 2010 utilisant l’accès utilisateur à distance (en se connectant à Lync Server 2010 en dehors de l’intranet mais sans VPN) avec un utilisateur sur Lync Server 2013 et un utilisateur sur Lync Server 2010. Testez la messagerie instantanée (IM), la présence, l’audio/vidéo (A/V) et le partage de Bureau.

  - Utilisateur hébergé sur Lync Server 2013 utilisant l’accès utilisateur à distance (en se connectant à Lync Server 2013 en dehors de l’intranet mais sans VPN) avec un utilisateur sur Lync Server 2013 et un utilisateur sur Lync Server 2010. Testez la messagerie instantanée (IM), la présence, l’audio/vidéo (A/V) et le partage de Bureau.

