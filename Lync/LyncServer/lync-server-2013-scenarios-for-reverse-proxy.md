---
title: 'Lync Server 2013 : scénarios pour le proxy inverse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 767df1e427cd29e9437b4bd04d2859b382b48267
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510831"
---
# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a>Scénarios de proxy inverse dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-21_

Les proxys inverses sont requis dans Lync Server 2013 pour permettre l’accès aux services et aux ressources, tels que les URL simples de rendez-vous, le carnet d’adresses, le contenu de la réunion, le développement de listes de distribution, les services de mobilité, etc. Le scénario classique de proxy inverse dans Lync Server 2013 est de permettre aux clients externes (par exemple, le client de bureau ou le client Lync Web App) d’accéder au directeur ou aux services Web externes du serveur frontal.

**Proxy inverse et services Web externes**

![13142405-D5C9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-D5C9-45b7-a8b7-a8c89f09c97c")

Lors de la phase de planification, vous définissez les conditions requises pour le proxy inverse dans un déploiement Lync Server 2013. Le proxy inverse permet l’accès aux fonctionnalités pour les clients externes suivants :

  - Client de bureau Microsoft Lync 2013

  - Microsoft Lync Web App

  - Microsoft Lync Mobile

  - Application Lync du Windows Store

Lors de la planification de votre déploiement Lync Server 2013, vous mappez les configurations réelles requises pour Lync Server 2013 aux fonctionnalités de proxy inverse.

1.  Les clients externes se connecteront au proxy inverse sur le port TCP 443 et utiliseront SSL (Secure Socket Layer) ou TLS (Transport Layer Security). Les clients mobiles Microsoft Lync peuvent se connecter au port TCP 80, mais uniquement lors de la connexion initiale aux services de découverte Lync et l’administrateur a configuré les enregistrements CNAMe (ou alias) DNS (Domain Name System) appropriés et accepte que cette communication ne soit pas chiffrée.

2.  Les services Web externes de Lync Server 2013 (déployés sur le serveur frontal et/ou le directeur) attendent une connexion à partir d’un proxy inverse sur le port TCP 4443 et il s’attend à ce que la connexion soit SSL/TLS.
    
    <div>
    

    > [!IMPORTANT]  
    > Les ports d’écoute par défaut suggérés pour les services Web externes sont TCP 8080 pour le trafic HTTP et TCP 4443 pour le trafic HTTPs. Le générateur de topologies offre la possibilité de remplacer les paramètres par défaut et de définir vos propres ports d’écoute pour les services Web externes. Il est important de noter que le proxy inverse communique avec les services Web externes, et que les clients externes communiquent avec le proxy inverse. Le client externe communique avec le proxy inverse sur le port TCP 443, mais vous pouvez redéfinir le port auquel le proxy inverse communique avec les services Web externes. Les options du générateur de topologies pour remplacer les ports d’écoute par défaut des services Web vous permettent de résoudre les conflits de ports d’écoute pouvant se produire dans votre infrastructure.

    
    </div>

3.  Les services Web externes de Lync Server 2013 attendent que le client ait un en-tête d’hôte non modifié pour identifier le service et l’annuaire du serveur Web que le client essaie d’utiliser. Les demandes doivent apparaître comme si elles provenaient du proxy inverse.

4.  Les services Web externes utilisent des répertoires virtuels de serveur Web définis (vDir) qui fournissent les services offerts aux clients. Les services Web identifiables de manière externe spécifiques sont les suivants :
    
      - VDir pour les réunions de conférence Web
    
      - La vDir « numérotation » pour l’accès téléphonique et la téléconférence
    
      - L’vDir de découverte automatique pour l’application Lync Windows Store, Lync mobile et le client de bureau Lync 2013. Le service de découverte automatique dans Lync Server 2013 est connu sous le nom DNS « lyncdiscover ».
    
      - Les services non définis sont accessibles par le client externe via des appels directs aux services Web externes. Par exemple, l’expansion de groupe de distribution (DLX) et le service de carnet d’adresses (ABS) sont accédés par des appels directs aux services Web externes et aux vDirs associés. Le client connaît le chemin d’accès réel au vDir et construit un localisateur d’enregistrement uniforme (URL) en fonction de ces informations. Le client accède au service de carnet d’adresses à l’aide d’une URL semblable à `https://externalweb.contoso.com/abs/handler`
    
      - Office Web Apps Server lorsque la Conférence est définie et configurée dans le cadre de la topologie Lync Server
        
        <div>
        

        > [!NOTE]  
        > Office Web Apps Server est un serveur de rôles distinct et n’est pas configuré dans le cadre des services Web externes. Ce serveur est publié séparément pour l’accès au client.

        
        </div>

5.  Définissez le pontage SSL pour chaque service. Le port externe TCP 443 est mappé au port de services Web externes de TCP 4443. Pour le protocole HTTP non chiffré, le port TCP 80 est mappé au port TCP 8080 des services Web externes

6.  Planifier les écouteurs de proxy inverse pour publier des ressources de serveur Web

7.  Demandez et configurez le certificat pour le proxy inverse en fonction des services qui seront proposés. S’il est configuré avec les autres noms de sujet corrects, ce certificat peut être partagé par tous les écouteurs configurés sur le serveur proxy inverse.

Ressources disponibles pour planifier le déploiement de votre proxy inverse :

  - [Collecte de données dans Lync Server 2013](lync-server-2013-data-collection.md)

  - [Résumé des certificats-proxy inverse dans Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Résumé des ports-proxy inverse dans Lync Server 2013](lync-server-2013-port-summary-reverse-proxy.md)

  - [Résumé des enregistrements DNS-proxy inverse dans Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

