---
title: 'Lync Server 2013 : Prise en charge du protocole IP et de gestion réseau'
TOCTitle: Prise en charge du protocole IP et de gestion réseau
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412848(v=OCS.15)
ms:contentKeyID: 49298573
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prise en charge du protocole IP et de gestion réseau dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Lync Server 2013 prend en charge les protocoles IP et réseau suivants :

  - **Protocoles IP.**    Lync Server 2013 prend en charge IP version 4 (IPv4) ou IP version 6 (IPv6) pour le réseau du serveur.
    
    > [!NOTE]  
    > Lync Server 2013 peut fonctionner dans un réseau avec la double pile IP activée.

  - **Protocoles de transport SIP.**   En général, SIP peut utiliser au moins trois types de transport : UDP (User Datagram Protocol), TCP (Transmission Control Protocol) et TLS (Transport Layer Security). Dans la configuration de transport SIP par défaut, le protocole TLS prévaut sur TCP. TLS est utilisé sur le réseau Lync Server 2013. À la périphérie du réseau, Lync Server 2013 peut interagir par le biais du protocole TCP. Lync Server 2013 ne prend pas en charge le protocole UDP pour le transport SIP, car il ne respecte pas les normes minimales de sécurité, de fiabiilité et d’évolutivité. Pour plus d’informations, reportez-vous à l’article du blog NextHop intitulé « Utiliser ou non UDP, telle est la question », à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369).
    
    > [!NOTE]  
    > Le contenu des blogs et leurs URL peuvent être modifiés sans préavis.
