---
title: 'Lync Server 2013 : Configuration requise pour le service de découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea9d9be05561d200696a5ad0256c0d5424cf9b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a>Configuration requise pour le service de découverte automatique pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-25_

Le service de découverte automatique Microsoft Lync Server 2013 s’exécute sur le directeur et les serveurs du pool frontal, et lorsqu’il est publié en DNS, il est possible d’utiliser les appareils mobiles exécutant Lync mobile pour localiser les services de mobilité. Pour que les appareils mobiles exécutant Lync mobile puissent bénéficier de la découverte automatique, vous devez modifier les listes de noms de remplacement de l’objet du certificat sur tout directeur et serveur frontal exécutant le service de découverte automatique. Par ailleurs, il est possible que vous deviez modifier les listes nom de remplacement de l’objet sur les certificats utilisés pour les règles de publication de service Web externe sur les proxys inverses.

Pour plus d’informations sur les entrées de nom alternatif requises pour les directeurs, les serveurs frontaux et les proxys inversés, voir [configuration technique requise pour la mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) pour la planification de la mobilité.

La décision concernant l’utilisation des listes de noms secondaires d’objet sur les proxys inversés est basée sur le fait que vous publiez le service de découverte automatique sur le port 80 ou sur le port 443:

  - **Publié sur le port 80**   , aucune modification de certificat n’est requise si la requête initiale au service de découverte automatique a lieu sur le port 80. En effet, les appareils mobiles exécutant Lync accèderont au proxy inverse sur le port 80 en externe, puis seront redirigés vers un serveur directeur ou frontal sur le port 8080 en interne. Pour plus d’informations, voir la section «découverte automatique du processus avec le port 80» plus loin dans cette rubrique.

  - **Publié sur le port 443**   la liste autre nom de l’objet sur les certificats utilisés par la règle de publication des services Web externes doit contenir un *lyncdiscover.\< entrée\> sipdomain* pour chaque domaine SIP au sein de votre organisation.

La réémission de certificats à l’aide d’une autorité de certification interne est généralement un processus simple, mais pour les certificats publics utilisés sur la règle de publication de service Web, l’ajout de plusieurs entrées de nom de sujet alternatif peut devenir coûteux. Pour contourner ce problème, nous prenons en charge la connexion automatique de découverte automatique sur le port 80, qui est ensuite redirigée vers le port 8080 du directeur ou du serveur principal.

Par exemple, supposons qu’un client mobile exécutant Lync mobile est configuré de manière à se connecter à Lync Server 2013 à l’aide de la fonctionnalité de détection automatique qui utilise HTTP pour la requête initiale.

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a>Processus de découverte automatique initial pour les appareils mobiles utilisant le port 80

1.  Périphérique mobile exécutant Lync mobile recherche lyncdiscover.contoso.com à l’aide de DNS, où existe un enregistrement A.

2.  Le DNS externe renvoie l’adresse IP des services Web externes au client.

3.  Le périphérique mobile exécutant Lync mobile envoie http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com une demande au proxy inverse

4.  La règle de publication Web va lier la demande du port 80 en externe au port 8080 en interne, ce qui permettra alors de la diriger vers un directeur ou un serveur frontal.
    
    Dans la mesure où la requête est HTTP et non HTTPs, aucune modification n’est nécessaire pour le certificat sur la règle de publication de service Web externe pour la prise en charge du service de découverte automatique.

5.  Le service de découverte automatique renvoie les URL du service Web externe (au format HTTP).

6.  L’appareil mobile exécutant Lync mobile peut ensuite se reconnecter au proxy inverse sur le port 443 et être redirigé sur 4443 vers le service de mobilité qui s’exécute sur le pool de domicile de l’utilisateur.
    
    Dans la mesure où la requête HTTPs s’applique aux URL des services Web externes par rapport à l’URL du service de découverte automatique, elle réussit, car le certificat comporte déjà des entrées de nom de domaine complet (FQDN) pour les services Web externes.
    
    Dans ce scénario, il n’y a aucune modification de certificat requise pour prendre en charge la mobilité.
    
    <div>
    

    > [!NOTE]  
    > Si le serveur Web cible possède un certificat qui ne possède pas de valeur correspondante pour lyncdiscover.contoso.com en tant que valeur de la liste autre nom d’objet:<BR>un serveur&nbsp;&nbsp;&nbsp;. Web répond avec un «serveur Hello» et aucun certificat.<BR>b.&nbsp;&nbsp;&nbsp;l’appareil mobile exécutant Lync mobile met immédiatement fin à la session.<BR>Si le serveur Web cible possède un certificat qui inclut lyncdiscover.contoso.com comme valeur de liste autre nom d’objet:<BR>un serveur&nbsp;&nbsp;&nbsp;. Web répond avec un «serveur Hello» et un certificat.<BR>b.&nbsp;&nbsp;&nbsp;l’appareil mobile exécutant Lync mobile valide le certificat et termine le transfert.

    
    </div>

Pour prendre en charge une connexion initiale au service de découverte automatique à l’aide du port 80 sur votre serveur proxy inverse, vous pouvez créer une règle de publication http similaire à cet exemple pour une règle de publication Web de proxy 2010 inverse:

1.  Créer une nouvelle règle de publication Web (par exemple, **découverte automatique de Lync Server (http)**).

2.  Dans **nom public**, entrez lyncdiscover.contoso.com.

3.  Dans l’onglet **pontage** , sélectionnez uniquement la possibilité de lier les requêtes du port 80 au port 8080.

4.  Dans l’onglet **authentification** , sélectionnez **aucune authentification**, et le **client ne peut pas s’authentifier directement**.

5.  Valider les modifications et déplacer la règle vers le haut de la liste des règles Lync (tout d’abord dans l’ordre de traitement).

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>Mobilité pour le déploiement de domaines fractionnés

Un espace d’adressage SIP partagé, également connu sous le nom de *domaine fractionné*, ou *déploiement hybride* est une configuration dans laquelle les utilisateurs sont déployés dans un déploiement local et un environnement en ligne. Le résultat escompté consiste à disposer d’un utilisateur, où qu’il se trouve (en local ou en ligne), à se connecter au déploiement et à être redirigé vers son emplacement du serveur d’origine. Pour ce faire, la fonctionnalité de découverte automatique de Microsoft Lync Server 2013 est utilisée pour rediriger l’utilisateur en ligne vers la topologie en ligne. Pour ce faire, vous configurez l’URL (Uniform Resource Locator) de découverte automatique à l’aide de Lync Server Management Shell et des applets **de cmdlet Get-CsHostingProvider** et **Set-CsHostingProvider**.

Vous devrez collecter et enregistrer les attributs déployés suivants:

  - À partir de Lync Server Management Shell, tapez
    
        Get-CsHostingProvider

  - Dans les résultats, recherchez le fournisseur en ligne doté de l’attribut **ProxyFQDN**. Par exemple, sipfed.online.lync.com

  - Enregistrer la valeur de ProxyFQDN

  - Activer la Fédération dans le panneau de configuration de Lync Server sur site, autorisant la Fédération avec le fournisseur en ligne

  - Activez la Fédération pour le fournisseur en ligne. Par défaut, tous les utilisateurs en ligne sont activés pour la Fédération de domaine et peuvent communiquer avec tous les domaines

  - Si vous définissez des domaines bloqués et autorisés, déterminez les domaines que vous autorisez explicitement ou bloquez explicitement.

  - Pour la Fédération en ligne, vous devez prévoir des exceptions de pare-feu, des certificats et l’hôte DNS (A ou AAAA, si vous utilisez des enregistrements IPv6). Par ailleurs, vous devez configurer des stratégies de Fédération. Pour plus d’informations, reportez-vous [à planification de Lync server 2013 et Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

