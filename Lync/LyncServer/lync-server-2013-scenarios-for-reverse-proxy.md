---
title: 'Lync Server 2013 : Scénarios de proxy inverse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1621e8bb0241e82f9f4678d4fe39a4f66f6bcf9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a>Scénarios de proxy inverse dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-01-21_

Les proxys inversés sont requis dans Lync Server 2013 pour permettre l’accès aux services et aux ressources tels que la réunion et les URL de connexion, le carnet d’adresses, le contenu de la réunion, le développement de la liste de distribution, les services de mobilité, etc. Le scénario classique de proxy inverse dans Lync Server 2013 consiste à autoriser les clients externes (par exemple, le client de bureau ou le client Lync Web App) à accéder au directeur ou aux services Web externes du serveur frontal.

**Proxy inverse et services Web externes**

![13142405-D5C9-45b7-a8b7-a8c89f09c97c] (images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-D5C9-45b7-a8b7-a8c89f09c97c")

Pendant la phase de planification, vous définissez les exigences du proxy inverse dans un déploiement 2013 de Lync Server. Le proxy inverse autorise l’accès à des fonctionnalités pour les clients externes suivants:

  - Client de bureau Microsoft Lync 2013

  - Microsoft Lync Web App

  - Microsoft Lync Mobile

  - application Lync du Windows Store

Lors de la planification du déploiement de Lync Server 2013, vous mappez la configuration requise réelle pour Lync Server 2013 aux fonctionnalités de proxy inverse.

1.  Les clients externes se connectent au proxy inverse sur le port TCP 443 et utiliseront SSL (Secure Socket Layer) ou TLS (Transport Layer Security). Les clients mobiles Microsoft Lync peuvent se connecter au port TCP 80, mais uniquement lors de l’exécution d’une connexion initiale aux services de découverte de Lync et l’administrateur a configuré les enregistrements de nom de domaine (ou alias) appropriés, et l’accepte la communication ne sera pas chiffrée.

2.  Les services Web externes de Lync Server 2013 (déployés sur le serveur frontal et/ou le directeur) attendent une connexion d’un proxy inverse sur le port TCP 4443 et il s’attend à ce que la connexion soit SSL/TLS.
    
    <div>
    

    > [!IMPORTANT]  
    > Les ports d’écoute par défaut suggérés pour les services Web externes sont TCP 8080 pour le trafic HTTP et TCP 4443 pour le trafic HTTPs. Le générateur de topologie donne la possibilité de remplacer les valeurs par défaut et de définir vos propres ports d’écoute pour les services Web externes. Il est important de noter que le proxy inverse communique avec les services Web externes et que les clients externes communiquent avec le proxy inverse. Le client externe communique avec le proxy inverse sur le port TCP 443, mais vous pouvez redéfinir le port que le proxy inverse communique avec les services Web externes. Les options du générateur de topologie pour remplacer les ports d’écoute par défaut des services Web vous permettent de résoudre les conflits de port d’écoute qui peuvent se produire dans votre infrastructure.

    
    </div>

3.  Les services Web externes de Lync Server 2013 attendent un en-tête d’hôte non modifié du client pour identifier le service et l’annuaire du serveur Web que le client tente d’utiliser. Les demandes doivent apparaître comme si elles provenaient du proxy inverse.

4.  Les services Web externes utilisent des répertoires virtuels définis par le Web Server (vDir), qui fournissent les services offerts aux clients. Les services Web d’identification externes spécifiques sont les suivants:
    
      - VDir pour les réunions de conférences Web
    
      - Le vDir «Dial» pour l’accès téléphonique et la conférence téléphonique
    
      - L’vDir de découverte automatique pour l’application Lync du Windows Store, la version mobile de Lync et le client de bureau Lync 2013. Le système de découverte automatique de Lync Server 2013 est connu sous le nom DNS «lyncdiscover»
    
      - Les services non définis sont accessibles par le client externe par le biais des appels directs vers les services Web externes. Par exemple, l’extension du groupe de distribution (DLX) et le service de carnet d’adresses (ABS) sont accessibles par des appels directs aux services Web externes et des vDirs associés. Le client connaît le chemin réel vers vDir et crée un localisateur d’enregistrements uniformes (URL) en fonction de ces informations. Le client accède au service de carnet d’adresses à l’aide d’une URL semblable à`https://externalweb.contoso.com/abs/handler`
    
      - Serveur Office Web Apps lorsque la Conférence est définie et configurée dans le cadre de la topologie du serveur Lync
        
        <div>
        

        > [!NOTE]  
        > Office Web Apps Server est un serveur de rôles distinct et n’est pas configuré dans le cadre des services Web externes. Ce serveur est publié séparément pour l’accès client.

        
        </div>

5.  Définissez le pontage SSL pour chaque service. Le port externe TCP 443 est mappé au port de services Web externes de TCP 4443. Pour le protocole HTTP non chiffré, le port TCP 80 est mappé au port TCP 8080 de port de services Web externes

6.  Planifier des écouteurs de proxy inversés pour publier des ressources de serveur Web

7.  Demandez et configurez le certificat de proxy inverse en fonction des services qui seront proposés. S’il est configuré avec le nom correct de l’objet, ce certificat peut être partagé par tous les écouteurs configurés du serveur proxy inverse.

Ressources disponibles pour la planification de votre déploiement de proxy inverse:

  - [Collecte des données dans Lync Server 2013](lync-server-2013-data-collection.md)

  - [Résumé des certificats - Proxy inverse dans Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Résumé des ports - Proxy inverse dans Lync Server 2013](lync-server-2013-port-summary-reverse-proxy.md)

  - [Résumé DNS - Proxy inverse dans Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

