---
title: Considérations relatives à l’interopérabilité pour les conférences vidéo
TOCTitle: Considérations relatives à l’interopérabilité pour les conférences vidéo
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204790(v=OCS.15)
ms:contentKeyID: 49296802
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Considérations relatives à l’interopérabilité pour les conférences vidéo

 

_**Dernière rubrique modifiée :** 2012-10-02_

Cette section décrit l’expérience utilisateur pendant la phase de coexistence de la migration, c’est-à-dire quand les clients hérités interagissent avec un pool Lync Server 2013 ou que les clients Lync Server 2013 interagissent avec un pool hérité.

## Pools Lync Server 2013

Les utilisateurs constatent le comportement suivant quand un client hérité est utilisé dans un pool Lync Server 2013 :

  - Pour les appels à deux, la résolution vidéo est la même que dans le pool hérité.

  - Pour les conférences à plusieurs, la résolution vidéo et les fonctionnalités de vidéoconférence sont les mêmes que celles du pool hérité. La vue Galerie et la haute résolution ne sont pas disponibles.

## Pools hérités

Les utilisateurs constatent le comportement suivant quand un client Lync Server 2013 est utilisé dans un pool hérité :

  - Pour les appels à deux, les clients Lync Server 2013 peuvent utiliser les nouvelles fonctionnalités suivantes :
    
      - H.264 est disponible si les deux participants utilisent des clients Lync Server 2013.
    
      - Le client Lync Server 2013 utilise la valeur par défaut de TotalReceiveVideoBitRateKb, car le serveur hérité n’envoie pas ces informations avec la mise en service intrabande.

  - Pour les conférences à plusieurs, la résolution vidéo et les fonctionnalités de vidéoconférence sont les mêmes que celles d’un client hérité dans le pool hérité.

> [!NOTE]  
> Quand un serveur hérité héberge un client Lync Server 2013, il est possible de configurer la bande passante réservée à la vidéoconférence de sorte que tous les utilisateurs du pool ne reçoivent qu’une vidéo basse résolution mais puissent envoyer une vidéo haute résolution. Par exemple, la valeur de MaxVideoRateAllowed est CIF-250K dans la configuration multimédia et celle de VideoBitRateKb est 2 000 Kbits/s dans la stratégie de conférence, dans ce scénario, les utilisateurs du pool ne peuvent pas bénéficier d’une haute résolution.<br />
MaxVideoRateAllowed n’étant plus utilisé pour les clients Lync Server 2013, il ne peut pas empêcher les clients Lync Server 2013 de demander des vidéos haute résolution. En revanche, vous pouvez affecter pour tous les utilisateurs du pool la même valeur à VideoBitRateKb et à MaxVideoRateAllowed (c’est-à-dire, CIF est défini sur 250 Kbits/s ou VGA est défini sur 600 Kbits/s ou HD est défini sur 1 500 Kbits/s).
