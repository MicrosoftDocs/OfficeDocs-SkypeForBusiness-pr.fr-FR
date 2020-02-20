---
title: 'Lync Server 2013 : configuration requise pour le service de découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dc50b7eedf6aa815c52b44ed4c1ddb88cea5217
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a>Configuration requise pour le service de découverte automatique pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-25_

Le service de découverte automatique Microsoft Lync Server 2013 s’exécute sur les serveurs directeur et de pool frontal, et lorsqu’il est publié dans le système DNS, peut être utilisé par les appareils mobiles exécutant Lync mobile pour localiser les services de mobilité. Avant que les appareils mobiles exécutant Lync mobile puissent tirer parti de la découverte automatique, vous devez modifier les listes des autres noms de sujet du certificat sur un directeur et un serveur frontal exécutant le service de découverte automatique. En outre, il peut s’avérer nécessaire de modifier les listes des autres noms de sujet sur les certificats utilisés pour les règles de publication des services web externes sur les proxys inverses.

Pour plus d’informations sur les entrées des autres noms de sujet requises pour les directeurs, les serveurs frontaux et les proxys inverses, voir [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) dans Planning for Mobility.

La décision d’utiliser des listes d’autres noms de sujet sur les proxys inverses repose sur votre choix de publier le service de découverte automatique sur le port 80 ou sur le port 443 :

  - **Publié sur le port 80**   aucune modification de certificat n’est requise si la requête initiale du service de découverte automatique a lieu sur le port 80. Cela est dû au fait que les appareils mobiles exécutant Lync accèdent au proxy inverse sur le port 80 de manière externe, puis sont redirigés vers un directeur ou un serveur frontal sur le port 8080 en interne. Pour plus d’informations, consultez la section « Processus de découverte automatique initiale à l’aide du port 80 » plus loin dans cette rubrique.

  - **Publié sur le port 443**   la liste autre nom du sujet sur les certificats utilisés par la règle de publication des services Web externes doit contenir un *lyncdiscover.\< entrée\> sipdomain* pour chaque domaine SIP au sein de votre organisation.

La réémission de certificats à l’aide d’une autorité de certification interne constitue généralement un processus simple, mais pour les certificats publics utilisés dans la règle de publication des services web, l’ajout de plusieurs entrées d’autres noms de sujet peut s’avérer onéreux. Pour contourner ce problème, nous prenons en charge la connexion de découverte automatique initiale via le port 80, qui est ensuite redirigé vers le port 8080 sur le directeur ou le serveur frontal.

Par exemple, supposons qu’un client mobile exécutant Lync mobile est configuré pour se connecter à Lync Server 2013 à l’aide de la fonctionnalité de découverte automatique à l’aide du protocole HTTP pour la demande initiale.

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a>Processus de découverte automatique initiale pour les appareils mobiles utilisant le port 80

1.  Appareil mobile exécutant Lync mobile recherche lyncdiscover.contoso.com à l’aide de DNS, où se trouve un enregistrement A.

2.  DNS externe renvoie l’adresse IP pour les services Web externes au client.

3.  L’appareil mobile exécutant Lync mobile envoie http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com une demande au proxy inverse

4.  La règle de publication Web va relier la demande du port 80 de manière externe au port 8080 en interne, qui l’acheminera vers un directeur ou un serveur frontal.
    
    Étant donné qu’il s’agit d’une requête HTTP et non HTTPS, aucune modification n’est requise dans le certificat stipulé dans la règle de publication des services web externes afin de prendre en charge le service de découverte automatique.

5.  Le service de découverte automatique renvoie les URL des services web externes (au format HTTPS).

6.  L’appareil mobile exécutant Lync mobile peut alors se reconnecter au proxy inverse sur le port 443 et être redirigé sur 4443 vers le service de mobilité s’exécutant sur le pool d’accueil de l’utilisateur.
    
    Étant donné que la requête HTTPS concerne l’URL des services web externes par rapport à l’URL du service de découverte automatique, elle réussit car le certificat doit déjà contenir les entrées des autres noms de sujet pour les noms de domaine complets (FQDN) des services web externes.
    
    Dans ce scénario, aucune modification de certificat n’est requise pour prendre en charge la mobilité.
    
    <div>
    

    > [!NOTE]  
    > Si le serveur web cible possède un certificat qui ne dispose pas d’une adresse correspondant à lyncdiscover.contoso.com en tant que valeur de la liste des autres noms de sujet :<BR>un serveur&nbsp;&nbsp;&nbsp;. Web répond avec un « Server Hello » et aucun certificat.<BR>b.&nbsp;&nbsp;&nbsp;l’appareil mobile exécutant Lync mobile met immédiatement fin à la session.<BR>Si le serveur web cible possède un certificat qui comprend lyncdiscover.contoso.com comme valeur de la liste des autres noms de sujet :<BR>un serveur&nbsp;&nbsp;&nbsp;. Web répond avec un « serveur Hello » et un certificat.<BR>b.&nbsp;&nbsp;&nbsp;l’appareil mobile exécutant Lync mobile valide le certificat et termine le protocole de transfert.

    
    </div>

Pour prendre en charge une connexion initiale au service de découverte automatique utilisant le port 80 sur votre serveur proxy inverse, vous pouvez créer une règle de publication http similaire à cet exemple pour une règle de publication web de proxy inverse Forefront Threat Management Gateway 2010 :

1.  Créez une règle de publication web (par exemple, **Découverte automatique Lync Server (HTTP)**).

2.  Dans **Nom public**, entrez lyncdiscover.contoso.com.

3.  Sous l’onglet **Pontage**, sélectionnez uniquement l’option permettant d’établir un pont entre le port 80 et le port 8080 pour les requêtes.

4.  Sous l’onglet **Authentification**, sélectionnez **Aucune authentification** et **Le client ne peut pas s’authentifier directement**.

5.  Validez les modifications, puis déplacez la règle en haut de la liste des règles Lync (première dans l’ordre de traitement).

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>Mobilité pour le déploiement dans un domaine séparé

Un espace d’adressage SIP, également appelé *domaine séparé* ou *déploiement hybride* est une configuration dans laquelle les utilisateurs sont déployés sur site et dans un environnement en ligne. L’objectif est de permettre à un utilisateur, quel que soit l’emplacement de son serveur central (sur site ou en ligne), de se connecter au déploiement et d’être redirigé vers l’emplacement de son serveur central. Pour ce faire, la fonctionnalité de découverte automatique de Microsoft Lync Server 2013 est utilisée pour rediriger l’utilisateur en ligne vers la topologie en ligne. Pour ce faire, vous devez configurer l’URL (Uniform Resource Locator) de découverte automatique à l’aide de Lync Server Management Shell et des cmdlets **Get-CsHostingProvider** et **Set-CsHostingProvider**.

Vous devrez recueillir et enregistrer les attributs déployés suivants :

  - À partir de Lync Server Management Shell, tapez
    
        Get-CsHostingProvider

  - Dans les résultats, recherchez le fournisseur en ligne avec l’attribut **ProxyFQDN**. Par exemple, sipfed.online.lync.com.

  - Enregistrez la valeur de l’attribut ProxyFQDN.

  - Activer la Fédération dans le panneau de configuration Lync Server sur site, autorisant la Fédération avec le fournisseur en ligne

  - Activez la fédération pour le fournisseur en ligne. Par défaut, tous les utilisateurs en ligne sont activés pour la fédération de domaine et peuvent communiquer avec tous les domaines.

  - Si vous envisagez de définir les domaines bloqués et autorisés, déterminez les domaines que vous autoriserez et bloquerez de façon explicite.

  - Pour la fédération en ligne, vous devez planifier les exceptions de pare-feu, les certificats et les enregistrements d’hôte DNS (A ou AAAA, avec IPv6). En outre, vous devez configurer les stratégies de fédération. Pour plus d’informations, reportez-vous à la rubrique [Planning for Lync Server 2013 and Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

