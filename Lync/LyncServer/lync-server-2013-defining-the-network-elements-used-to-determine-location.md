---
title: 'Lync Server 2013 : définition des éléments réseau utilisés pour déterminer l’emplacement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6578c0cca54c41f079c682862b9e96a54e3d456
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a>Définition des éléments réseau utilisés pour déterminer l’emplacement dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-29_

Si vous configurez votre infrastructure Lync Server pour qu’elle prenne en charge la détection automatique de l’emplacement du client, vous devez d’abord décider des éléments réseau que vous allez utiliser pour mapper les appelants vers les emplacements. Dans Lync Server 2013, vous pouvez associer les éléments de réseau Layer 2 et Layer 3 suivants avec des emplacements :

  - Adresses BSSID (Basic Service Set Identification) des points d’accès sans fil (WAP) (couche 2)

  - Port commuté LLDP (couche 2)

  - ID de châssis commuté LLDP (couche 2)

  - Sous-réseaux IP (couche 3)

  - Adresses MAC des clients (couche 2)

Les éléments réseau sont répertoriés par ordre de priorité. Si un client peut être localisé à l’aide de plusieurs éléments réseau, Lync Server utilise l’ordre de priorité pour déterminer le mécanisme à utiliser.

Les sections suivantes abordent plus en détail l’utilisation de chaque élément réseau.

<div>


> [!IMPORTANT]  
> Lorsque vous utilisez des éléments réseau pour mapper des appelants vers des emplacements, il est très important de maintenir la base de données du service informations d’emplacement à jour. Par exemple, si vous ajoutez ou modifiez un élément réseau, comme un point d’accès sans fil, vous devez supprimer l’ancienne entrée et ajouter la nouvelle entrée dans la base de données d’emplacements.



</div>

<div>

## <a name="wireless-access-point"></a>Point d’accès sans fil

Lorsqu’un client se connecte au réseau via une liaison sans fil, la demande d’emplacement utilise l’adresse BSSID du point d’accès sans fil pour déterminer son emplacement. Si le client est en déplacement, le point d’accès sans fil indiqué risque de ne pas être le plus proche et il est même possible de sélectionner un point d’accès sans fil se trouvant à un autre étage du bâtiment. Pour indiquer que l’emplacement est approximatif, vous pouvez ajouter à la valeur de l’emplacement le descripteur Near ou Close to.

Cette méthode d’emplacement part du principe que le BSSID de chaque point d’accès sans fil est statique. Toutefois, si votre fournisseur de points d’accès sans fil utilise des BSSID attribués de manière dynamique, le BSSID obtenu auprès d’un point d’accès sans fil peut changer (cela peut se produire suite à une modification de configuration du point d’accès), et les clients sans fil peuvent se retrouver en situation de ne pas recevoir d’emplacement. Pour éviter cette possibilité, vous devez remplir la base de données du service informations d’emplacement avec ERL pour toutes les adresses BSSID possibles utilisées par chaque WAP.

</div>

<div>

## <a name="lldp-ports-and-switches"></a>Ports et commutateurs LLDP

Les commutateurs Ethernet gérés qui prennent en charge le protocole LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) peuvent annoncer leur identité et leurs informations de port aux clients compatibles LLDP-MED, lesquelles peuvent alors faire l’objet d’une requête dans la base de données d’emplacements afin de fournir l’emplacement du périphérique. Vous pouvez associer des ERL uniquement sur l’ID du châssis commuté, ou les mapper au niveau du port.

<div>


> [!NOTE]  
> Lync Server 2013 prend en charge l’utilisation de LLDP-MED pour la détermination des emplacements uniquement des appareils Lync Phone Edition et de Lync 2013 exécutés sur Windows 8. Si vous devez utiliser des données de couche 2 de niveau commutateur pour déterminer l’emplacement d’autres clients Lync à PC câblés, vous devez utiliser la méthode d’adresse MAC cliente.



</div>

</div>

<div>

## <a name="subnet"></a>Sous-réseau

Les sous-réseaux IP de couche 3 fournissent un mécanisme pris en charge par tous les clients Lync Server qui peut être utilisé pour détecter automatiquement l’emplacement du client. L’utilisation de sous-réseaux IP constitue la méthode d’emplacement la plus simple pour configurer et gérer des clients câblés. Avant d’opter pour l’utilisation de sous-réseaux, en revanche, répondez aux questions suivantes pour déterminer si la spécificité de l’emplacement du sous-réseau est suffisamment fine pour localiser un client avec précision :

  - Un ou plusieurs sous-réseaux des clients couvrent-ils plusieurs étages ?

  - Un ou plusieurs sous-réseaux couvrent-t-ils plusieurs immeubles ?

  - Quelle est la surface couverte par chaque sous-réseau client ?

Si le sous-réseau couvre une zone trop vaste, vous devrez envisager d’utiliser un autre mécanisme pour localiser les clients. Toutefois, si possible, nous recommandons aux clients de réorganiser leur sous-réseau IP afin de respecter les exigences de spécificité d’emplacement ERL plutôt que d’induire le coût et la complexité des solutions SNMP tierces.

</div>

<div>

## <a name="client-mac-address"></a>Adresse MAC d’un client

Pour utiliser l’adresse MAC d’un ordinateur client pour localiser un appelant, vous avez besoin de commutateurs Ethernet gérés, et vous devez déployer une solution SNMP tierce capable de découvrir les adresses MAC des clients Lync connectés à (ou via) ces commutateurs. La solution SNMP interroge continuellement les commutateurs gérés pour obtenir les mappages actuels des adresses MAC de point de terminaison connectées à chaque port et obtient les IP de port correspondants. Pendant la demande d’un client Lync au service d’informations d’emplacement, le service informations d’emplacement interroge l’application tierce à l’aide de l’adresse MAC du client, puis renvoie les ID de port et les adresses IP Switch correspondantes. Le service d’informations d’emplacement utilise ces informations pour interroger son câblage de couche 2 publié pour un enregistrement correspondant et renvoie l’emplacement au client. Si vous utilisez cette option, vérifiez que les identifiants de port de commutateur sont cohérents entre l’application SNMP et les enregistrements de la base de données d’emplacements publiés.

<div>


> [!NOTE]  
> Certaines solutions SNMP tierces peuvent prendre en charge les commutateurs d’accès non gérés ; si le commutateur qui dessert le client Lync est non géré mais comporte une liaison montante vers un commutateur de distribution géré, le commutateur géré peut signaler à l’application SNMP les adresses MAC des clients connectés au commutateur d’accès. Ces informations permettent au service d’informations d’emplacement d’identifier l’emplacement de l’utilisateur. Toutefois, il est possible d’affecter un seul ERL à tous les ports sur le commutateur non géré, afin que la spécificité de l’emplacement soit disponible uniquement au niveau du châssis du commutateur d’accès, et non au niveau du port.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

