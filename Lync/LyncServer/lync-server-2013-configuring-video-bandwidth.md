---
title: 'Lync Server 2013 : configuration de la bande passante vidéo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8995f47ff1059921c324d71cbaca26fa47c50ca0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a>Configuration de la bande passante vidéo dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

Lync Server 2013 comprend plusieurs paramètres de gestion de la vidéo pour les appels à deux et les conférences à plusieurs. Lorsque vous déployez Lync Server 2013, vous devez évaluer si les paramètres par défaut sont appropriés pour votre organisation et les modifier si nécessaire.

Les paramètres décrits dans cette section s’appliquent à la fois aux appels entre deux interlocuteurs et aux conférences entre plusieurs participants. Affichez ou modifiez ces paramètres à l’aide de l’une des applets de commande suivantes :

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Vérifiez les paramètres suivants dans votre stratégie de conférence :

  - **VideoBitRateKb**   ce paramètre spécifie la vitesse de transmission vidéo maximale en kilobits par seconde (Kbits/s) utilisée pour la vidéo envoyée par un utilisateur. La valeur par défaut est de 50 000 Kbits/s. Les valeurs valides sont comprises entre 0 et 50 000.
    
    Ce paramètre s’applique séparément à la vidéo principale et à la vidéo panoramique.
    
    Exemple : Si vous spécifiez 2000 kbits/s, Lync Server peut envoyer 2000 kbits/s pour le flux vidéo principal et 2000 kbits/s pour le flux vidéo panoramique.
    
    <div>
    

    > [!NOTE]  
    > La bande passante de réseau vidéo maximale pour un point de terminaison Lync 2013 est de 8000 Kbits/s pour la vidéo principale et de 2500 kbits/s pour la vidéo panoramique. Ces valeurs maximales ne sont atteintes que si plusieurs vidéos sont reçues ou envoyées. Pour plus d’informations, reportez-vous à la section « utilisation du réseau multimédia » dans la <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">bande passante réseau requise pour le trafic multimédia dans Lync Server 2013</A>. Cette section indique la bande passante maximale et classique du flux vidéo pour toutes les résolutions prises en charge.

    
    </div>

  - **TotalReceiveVideoBitRateKb**   ce paramètre, qui est nouveau dans Lync Server 2013, spécifie la vitesse de transmission maximale autorisée (en kilobits par seconde) pour tous les flux vidéo reçus par un client. En d’autres termes, il indique le total de tous les flux vidéo, à l’exception des flux vidéo panoramiques, qu’un client peut recevoir. Par exemple, si vous spécifiez 1 500 Kbits/s, le client peut recevoir jusqu’à 1 500 Kbits/s de vidéo, qui peuvent être constitués de plusieurs flux vidéo ou d’un seul flux vidéo. Ce paramètre s’applique uniquement aux clients Lync Server 2013.
    
    La valeur par défaut de **TotalReceiveVideoBitRateKb** est 50 000 Kbits/s. Si le paramètre **EnableMultiviewJoin** de la vue Galerie a la valeur True, **TotalReceiveVideoBitRateKb** ne doit pas être inférieur à 420 Kbits/s. Si le paramètre **EnableMultiviewJoin** de la vue Galerie a la valeur False, **TotalReceiveVideoBitRateKb** ne doit pas être inférieur à 100 Kbits/s. Si **EnableMultiviewJoin** a la valeur True et si la valeur que vous définissez est inférieure à 420 Kbits/s, la valeur seuil est affectée par défaut. Ce seuil permet d’éviter une erreur de configuration involontaire qui pourrait entraîner une mauvaise expérience utilisateur.
    
    <div>
    

    > [!NOTE]  
    > Pour plus d’informations sur le paramètre <STRONG>EnableMultiviewJoin</STRONG> , voir <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.

    
    </div>

  - **MaxVideoConferencingResolution**   ce paramètre n’est plus utilisé pour les clients Lync Server 2013 dans les conférences Lync Server 2013. Les conférences Lync Server 2013 utilisent les contrôles de vitesse de transmission décrits plus haut dans cette section. Ce paramètre est toujours utilisé pour les clients hérités qui rejoignent une conférence Lync Server 2013. Ce paramètre détermine la résolution maximale autorisée pour les clients hérités dans les conférences organisées par les utilisateurs hébergés sur Lync Server 2013. Autrement dit, les clients hérités sont traités de la même manière que dans les versions précédentes de Lync Server ou d’Office Communications Server.

Outre les paramètres de stratégie de conférence qui s’appliquent aux utilisateurs, évaluez les paramètres de configuration multimédia. Affichez ou modifiez ces paramètres à l’aide de l’une des applets de commande suivantes :

  - **Get-CsMediaConfiguration**

  - **Set-CsMediaConfiguration**

  - **New-CsMediaConfiguration**

Vérifiez le paramètre suivant :

  - **MaxVideoRateAllowed**   ce paramètre par pool spécifie le débit maximal auquel les signaux vidéo seront transférés aux points de terminaison du client. Il s’applique uniquement aux versions précédentes des clients Lync Server.
    
    <div>
    

    > [!NOTE]  
    > Les clients Lync Server 2013 ignorent ce paramètre et utilisent à la place le paramètre TotalReceiveVideoBitRateKb dans la stratégie de conférence.

    
    </div>
    
    La valeur par défaut est HD720P. Les valeurs valides sont HD720p15M, VGA600K et CIF250K.
    
    Exemple : si vous spécifiez 1 500 Kbits/s, tous les clients hérités du pool peuvent recevoir jusqu’à 1 500 Kbits/s de vidéo lors des conférences entre deux interlocuteurs et plus.

Les procédures suivantes sont des exemples d’utilisation de Lync Server Management Shell pour modifier les paramètres décrits dans cette section.

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a>Pour modifier la stratégie de conférence des paramètres vidéo

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  À partir de la ligne de commande, exécutez l’applet de commande suivante pour modifier la stratégie de conférence :
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a>Pour modifier la configuration multimédia des clients hérités

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  À partir de la ligne de commande, exécutez l’applet de commande suivante pour modifier la configuration multimédia :
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

