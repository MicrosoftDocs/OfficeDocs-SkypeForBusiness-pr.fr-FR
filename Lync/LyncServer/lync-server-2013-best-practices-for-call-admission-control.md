---
title: "Lync Server 2013 : Meill. pratiques liées au contrôle d’admission des appels"
TOCTitle: Meilleures pratiques liées au contrôle d’admission des appels
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398770(v=OCS.15)
ms:contentKeyID: 49298162
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Meilleures pratiques liées au contrôle d’admission des appels dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-22_

Pour améliorer les performances et faciliter le déploiement, appliquez les recommandations suivantes lors du déploiement du contrôle d’admission des appels :

  - Vérifiez que les réseaux étendus (WAN) sont configurés en conséquence pour le trafic multimédia actuel et envisagé.
    
    > [!NOTE]  
    > Nous vous conseillons de définir un facteur en mémoire tampon quant aux limites de votre bande passante. Il existe des scénarios de condition de concurrence qui agissent sur la bande passante totale utilisée et qui peuvent entraîner des situations de dépassement de la limite de la bande. Prenons l’exemple de deux appels amorcés alors que le trafic multimédia approche de la limite de la bande passante : l’un des appels pourra être refusé, car l’autre a été configuré pour démarrer en premier.

  - Contrôlez l’utilisation du réseau et les enregistrements des détails des appels pour pouvoir choisir les meilleurs paramètres de contrôle d’admission des appels (CAC) et les mettre à jour en fonction de l’évolution de l’utilisation du réseau.

  - Utilisez les stratégies de bande passante CAC pour compléter les paramètres QoS.

  - Si vous souhaitez réacheminer des appels bloqués sur le réseau RTC, vérifiez les fonctionnalités et capacités correspondantes. Pour plus d’informations, reportez-vous à [Planification du routage des communications vocales sortantes dans Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).
    
    > [!NOTE]  
    > La capacité fait référence au nombre de ports à ouvrir pour prendre en charge un éventuel réacheminement vers le réseau RTC.
