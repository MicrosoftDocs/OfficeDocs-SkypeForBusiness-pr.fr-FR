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
ms.openlocfilehash: 3cca8df1ea3c4c2458851da24ab8b39dbbab2d3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a>Configuration de la bande passante vidéo dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

Lync Server 2013 inclut plusieurs paramètres pour la gestion de la vidéo pour les appels et les conférences à plusieurs parties. Lorsque vous déployez Lync Server 2013, vous devez déterminer si les paramètres par défaut sont appropriés pour votre organisation, et les modifier si nécessaire.

Les paramètres décrits dans cette section s’appliquent aux appels à deux participants et aux conférences multiparties. Pour afficher ou modifier ces paramètres, utilisez l’une des applets de commande suivantes :

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Vérifiez les paramètres suivants dans votre stratégie de conférence :

  - **VideoBitRateKb**   ce paramètre spécifie le débit vidéo maximal en kilobits par seconde (Ko) utilisés pour la vidéo envoyé par un utilisateur. La valeur par défaut est 50000 kb/s. Les valeurs valides sont comprises entre 0 et 50000.
    
    Ce paramètre s’applique uniquement à la vidéo principale et à la vidéo panoramique.
    
    Exemple : Si vous spécifiez 2000 kbps, Lync Server peut envoyer 2000 kbps pour le flux vidéo principal et 2000 kbps pour le flux vidéo panoramique.
    
    <div>
    

    > [!NOTE]  
    > La bande passante réseau vidéo maximale pour un point de terminaison Lync 2013 est 8000 kbps pour la vidéo principale et 2500 kbps pour la vidéo panoramique. Ces valeurs maximales sont atteintes uniquement si plusieurs vidéos sont reçues ou envoyées. Pour plus d’informations, consultez la section « utilisation du réseau du trafic multimédia » dans <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">exigences de bande passante réseau pour le trafic multimédia dans Lync Server 2013</A>. Cette section répertorie la bande passante du flux vidéo maximal et standard pour toutes les résolutions prises en charge.

    
    </div>

  - **TotalReceiveVideoBitRateKb**   ce paramètre, qui est une nouveauté de Lync Server 2013, spécifie le débit maximal autorisé (en kilobits par seconde) pour tous les flux vidéo reçus par un client. C’est-à-dire qu’il spécifie le total combiné de tous les flux vidéo, à l’exception des flux vidéo panoramiques qu’un client peut recevoir. Par exemple, si vous spécifiez 1500 kbps, un client peut recevoir jusqu’à 1500 kbps de vidéo, ce qui peut être composé de plusieurs flux vidéo ou d’un seul flux vidéo. Ce paramètre s’applique uniquement aux clients Lync Server 2013.
    
    La valeur par défaut de **TotalReceiveVideoBitRateKb** est 50000 kbps. Si le paramètre **EnableMultiviewJoin** pour la vue Galerie est défini sur true, **TotalReceiveVideoBitRateKb** ne doit pas être défini sous 420 KB/s. Si le paramètre **EnableMultiviewJoin** pour la vue Galerie est défini sur false, **TotalReceiveVideoBitRateKb** ne doit pas être défini sous 100 kb/s. Si **EnableMultiviewJoin** est défini sur true et que vous définissez la valeur inférieure à 420 KB/s, les valeurs par défaut sont la valeur Threshold. Ce seuil permet d’éviter toute configuration intempestive qui peut entraîner une mauvaise utilisation de l’utilisateur.
    
    <div>
    

    > [!NOTE]  
    > Pour plus d’informations sur le paramètre <STRONG>EnableMultiviewJoin</STRONG> , voir <A href="lync-server-2013-configuring-gallery-view.md">configuration de l’affichage Galerie dans Lync Server 2013</A>.

    
    </div>

  - **MaxVideoConferencingResolution**   ce paramètre n’est plus utilisé pour les clients Lync Server 2013 dans les conférences Lync Server 2013. Les conférences Lync Server 2013 utilisent les contrôles de débit binaire décrits plus haut dans cette section. Ce paramètre est toujours utilisé pour les clients hérités qui rejoignent une conférence Lync Server 2013. Ce paramètre détermine la résolution maximale autorisée pour les clients hérités dans les conférences organisées par des utilisateurs hébergés sur Lync Server 2013. En d’autres termes, les clients hérités sont traités de la même façon que dans les versions précédentes de Lync Server ou d’Office Communications Server.

En plus des paramètres de stratégie de conférence qui s’appliquent aux utilisateurs, évaluez les paramètres de configuration multimédia. Pour afficher ou modifier ces paramètres, utilisez l’une des applets de commande suivantes :

  - **Get-CsMediaConfiguration**

  - **Set-CsMediaConfiguration**

  - **Nouveau-CsMediaConfiguration**

Vérifiez les paramètres suivants :

  - **MaxVideoRateAllowed**   ce paramètre par pool spécifie le taux maximal auquel les signaux vidéo sont transférés aux points de terminaison client. Il s’applique uniquement aux versions antérieures de clients Lync Server.
    
    <div>
    

    > [!NOTE]  
    > Les clients Lync Server 2013 ignorent ce paramètre et utilisent plutôt le paramètre TotalReceiveVideoBitRateKb de la stratégie de conférence.

    
    </div>
    
    La valeur par défaut est HD720P. Les valeurs valides sont HD720p15M, VGA600K et CIF250K.
    
    Exemple : Si vous spécifiez 1500 kbps, tous les clients hérités du pool peuvent recevoir jusqu’à 1500 kbps de vidéo dans le cadre de conférences à deux ou plusieurs parties.

Les procédures suivantes sont des exemples d’utilisation de Lync Server Management Shell pour modifier les paramètres décrits dans cette section.

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a>Pour modifier la stratégie de conférence pour les paramètres vidéo

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Dans la ligne de commande, exécutez l’applet de commande suivante pour modifier la stratégie de conférence :
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a>Pour modifier la configuration multimédia pour les clients hérités

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Dans la ligne de commande, exécutez l’applet de commande suivante pour modifier la configuration multimédia :
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

