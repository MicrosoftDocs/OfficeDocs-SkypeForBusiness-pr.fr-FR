---
title: "Lync Server 2013 : Coloc. de serveur pris en ch. pour les composants Edge"
TOCTitle: Colocalisation de serveur prise en charge pour les composants Edge
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425934(v=OCS.15)
ms:contentKeyID: 49297037
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Colocalisation de serveur prise en charge pour les composants Edge dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-08_

Le service Edge d’accès, le service Edge de conférence web, le service Edge A/V et le service proxy XMPP sont colocalisés sur des serveurs Edge. Les serveurs suivants fournissent les fonctions nécessaires à l’accès des utilisateurs externes et doivent être déployés en tant que serveurs dédiés :

  - Serveur Edge

  - Directeur (facultatif)

  - Proxy inverse

> [!IMPORTANT]  
> Le proxy inverse n’a pas besoin d’être dédié au traitement exclusif de Lync Server 2013. Par exemple, vous pouvez fournir des services pour publier les services web Lync Server et fournir en même temps un site web publié pour un autre site web qui n’a aucun impact on Lync Server. Si vous disposez déjà d’un serveur proxy inverse dans le réseau de périmètre pour la prise en charge d’autres services, vous pouvez l’utiliser pour Lync Server 2013.
