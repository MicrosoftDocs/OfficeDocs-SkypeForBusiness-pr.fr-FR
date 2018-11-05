---
title: Configuration de la bande passante vidéo dans Lync Server 2013
TOCTitle: Configuration de la bande passante vidéo dans Lync Server 2013
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204842(v=OCS.15)
ms:contentKeyID: 49297054
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la bande passante vidéo dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-02_

Lync Server 2013 comprend plusieurs paramètres de gestion vidéo pour les appels entre deux interlocuteurs et les conférences entre plusieurs participants. Quand vous déployez Lync Server 2013, vous devez évaluer si les paramètres par défaut sont appropriés pour votre organisation, et les modifier le cas échéant.

Les paramètres décrits dans cette section s’appliquent à la fois aux appels entre deux interlocuteurs et aux conférences entre plusieurs participants. Affichez ou modifiez ces paramètres à l’aide de l’une des applets de commande suivantes :

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Vérifiez les paramètres suivants dans votre stratégie de conférence :

  - **VideoBitRateKb**   Ce paramètre spécifie la vitesse de transmission vidéo maximale en kilobits par seconde (Kbits/s) utilisée pour la vidéo envoyée par un utilisateur. La valeur par défaut est de 50 000 Kbits/s. Les valeurs valides sont comprises entre 0 et 50 000.
    
    Ce paramètre s’applique séparément à la vidéo principale et à la vidéo panoramique.
    
    Exemple : si vous spécifiez 2 000 Kbits/s, Lync Server peut envoyer 2 000 Kbits/s pour le flux de la vidéo principale et 2 000 Kbits/s pour le flux de la vidéo panoramique.
    
    > [!NOTE]  
    > La bande passante réseau maximale en matière de vidéo pour un système d’extrémité Lync 2013 est de 8 000 Kbits/s pour la vidéo principale et de 2 500 Kbits/s pour la vidéo panoramique. Ces valeurs maximales ne sont atteintes que si plusieurs vidéos sont reçues ou envoyées. Pour plus d’informations, voir « Utilisation du réseau pour le trafic multimédia » dans <a href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Configuration requise de la bande passante pour le trafic multimédia dans Lync Server 2013</a>. Cette section indique la bande passante maximale et classique du flux vidéo pour toutes les résolutions prises en charge.

  - **TotalReceiveVideoBitRateKb**   Ce paramètre, qui est nouveau dans Lync Server 2013, spécifie la vitesse de transmission maximale autorisée (en Kbits/s) pour tous les flux vidéo reçus par un client. En d’autres termes, il indique le total de tous les flux vidéo, à l’exception des flux vidéo panoramiques, qu’un client peut recevoir. Par exemple, si vous spécifiez 1 500 Kbits/s, le client peut recevoir jusqu’à 1 500 Kbits/s de vidéo, qui peuvent être constitués de plusieurs flux vidéo ou d’un seul flux vidéo. Ce paramètre s’applique uniquement aux clients Lync Server 2013.
    
    La valeur par défaut de **TotalReceiveVideoBitRateKb** est 50 000 Kbits/s. Si le paramètre **EnableMultiviewJoin** de la vue Galerie a la valeur True, **TotalReceiveVideoBitRateKb** ne doit pas être inférieur à 420 Kbits/s. Si le paramètre **EnableMultiviewJoin** de la vue Galerie a la valeur False, **TotalReceiveVideoBitRateKb** ne doit pas être inférieur à 100 Kbits/s. Si **EnableMultiviewJoin** a la valeur True et si la valeur que vous définissez est inférieure à 420 Kbits/s, la valeur seuil est affectée par défaut. Ce seuil permet d’éviter une erreur de configuration involontaire qui pourrait entraîner une mauvaise expérience utilisateur.
    
    > [!NOTE]  
    > Pour plus d’informations sur le paramètre <strong>EnableMultiviewJoin</strong>, voir <a href="lync-server-2013-configuring-gallery-view.md">Configuration de la vue Galerie</a>.

  - **MaxVideoConferencingResolution**   Ce paramètre n’est plus utilisé pour les clients Lync Server 2013 dans les conférences Lync Server 2013. Les conférences Lync Server 2013 utilisent les contrôles de vitesse de transmission décrits plus haut dans cette section. Ce paramètre est toujours utilisé pour les clients hérités qui se joignent à une conférence Lync Server 2013. Ce paramètre détermine la résolution maximale autorisée pour les clients hérités dans les conférences organisées par des utilisateurs hébergés sur Lync Server 2013. En d’autres termes, les clients hérités sont traités comme dans les versions antérieures de Lync Server ou Office Communications Server.

Outre les paramètres de stratégie de conférence qui s’appliquent aux utilisateurs, évaluez les paramètres de configuration multimédia. Affichez ou modifiez ces paramètres à l’aide de l’une des applets de commande suivantes :

  - **Get-CsMediaConfiguration**

  - **Set- CsMediaConfiguration**

  - **New- CsMediaConfiguration**

Vérifiez le paramètre suivant :

  - **MaxVideoRateAllowed**   Ce paramètre spécifique au pool indique la vitesse maximale à laquelle les signaux vidéo sont transférés aux systèmes d’extrémité clients. Il s’applique uniquement aux versions antérieures des clients Lync Server.
    
    > [!NOTE]  
    > Les clients Lync Server 2013 ignorent ce paramètre et utilisent à la place le paramètre TotalReceiveVideoBitRateKb dans la stratégie de conférence.    
    
    
    La valeur par défaut est HD720P. Les valeurs valides sont HD720p15M, VGA600K et CIF250K.
    
    Exemple : si vous spécifiez 1 500 Kbits/s, tous les clients hérités du pool peuvent recevoir jusqu’à 1 500 Kbits/s de vidéo lors des conférences entre deux interlocuteurs et plus.

Les procédures suivantes sont des exemples d’utilisation de Lync Server Management Shell pour modifier les paramètres décrits dans cette section.

## Pour modifier la stratégie de conférence des paramètres vidéo

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  À partir de la ligne de commande, exécutez l’applet de commande suivante pour modifier la stratégie de conférence :
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

## Pour modifier la configuration multimédia des clients hérités

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  À partir de la ligne de commande, exécutez l’applet de commande suivante pour modifier la configuration multimédia :
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

