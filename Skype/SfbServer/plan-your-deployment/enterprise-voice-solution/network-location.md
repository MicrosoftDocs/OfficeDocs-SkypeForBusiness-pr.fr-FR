---
title: Définir les éléments de réseau permet de déterminer l’emplacement dans Skype Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: Décisions nécessaires pour planifier les composants réseau que vous allez utiliser pour mapper les appelants à des emplacements pour le déploiement de E9-1-1 dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 4cab36efdf0f4bcfbf3834e9c077558610655e3a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882305"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>Définir les éléments de réseau permet de déterminer l’emplacement dans Skype Business Server
 
Décisions nécessaires pour planifier les composants réseau que vous allez utiliser pour mapper les appelants à des emplacements pour le déploiement de E9-1-1 dans Skype pour Business Server Enterprise Voice.
  
Si vous configurez votre Skype pour infrastructure Business Server pour prendre en charge la détection automatique des clients de l’emplacement, vous devez d’abord décider quel réseau éléments que vous allez utiliser pour mapper les appelants à des emplacements. Dans Skype pour Business Server, vous pouvez associer les éléments suivants de réseau Layer 2 et 3 emplacements :
  
- Adresses BSSID (Basic Service Set Identification) des points d’accès sans fil (WAP) (couche 2)
    
- Port commuté LLDP (couche 2)
    
- ID de châssis commuté LLDP (couche 2)
    
- Sous-réseaux IP (couche 3)
    
- Adresses MAC des clients (couche 2)
    
Les éléments réseau sont répertoriés par ordre de priorité. Si un client peut se trouver à l’aide de plusieurs éléments réseau, Skype pour Business Server utilise l’ordre de priorité pour déterminer quel mécanisme à utiliser. 
  
Les sections suivantes abordent plus en détail l’utilisation de chaque élément réseau.
  
> [!IMPORTANT]
> Lorsque vous utilisez des éléments réseau pour mapper les appelants à des emplacements, il est primordiale conserver la base de données du service informations d’emplacement à jour. Par exemple, si vous ajoutez ou modifiez un élément réseau, comme un point d’accès sans fil, vous devez supprimer l’ancienne entrée et ajouter la nouvelle entrée dans la base de données d’emplacements. 
  
## <a name="wireless-access-point"></a>Point d’accès sans fil

Lorsqu’un client se connecte au réseau via une liaison sans fil, la demande d’emplacement utilise l’adresse BSSID du point d’accès sans fil pour déterminer son emplacement. Si le client est en itinérance, le WAP indiqué peut ne pas être celui le plus proche, et il est même possible de sélectionner un point d’accès qui se trouve sur un autre étage du bâtiment. Pour indiquer que l’emplacement est approximatif, vous pouvez ajouter la valeur d’emplacement avec un descripteur de **[près]** ou **[Fermer pour]** .
  
Cette méthode d’emplacement part du principe que le BSSID de chaque point d’accès sans fil est statique. Toutefois, si votre fournisseur WAP utilise BSSID affectées de manière dynamique, le BSSID est obtenu à partir d’un point d’accès peut changer (qui peut se produire après un changement de configuration WAP) et les clients sans fil peuvent se retrouver dans une situation où ils ne reçoivent pas un emplacement. Pour éviter cette possibilité, vous devez remplir la base de données service informations d’emplacement avec Erl de toutes les adresses BSSID possibles utilisés par chaque WAP. 
  
## <a name="lldp-ports-and-switches"></a>Ports et commutateurs LLDP

Les commutateurs Ethernet gérés qui prennent en charge le protocole LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) peuvent annoncer leur identité et leurs informations de port aux clients compatibles LLDP-MED, lesquelles peuvent alors faire l’objet d’une requête dans la base de données d’emplacements afin de fournir l’emplacement du périphérique. Vous pouvez associer des ERL uniquement sur l’ID du châssis commuté, ou les mapper au niveau du port.
  
> [!NOTE]
> Skype pour Business Server prend en charge les LLDP-MED pour déterminer les emplacements uniquement des appareils Lync Phone Edition et Skype pour les clients d’entreprise s’exécutant sur Windows 8. Si vous avez besoin utiliser les données de couche 2 au niveau du commutateur pour déterminer l’emplacement des autres câblé Skype sur PC pour les clients Business Server, vous devez utiliser la méthode d’adresse MAC client. 
  
## <a name="subnet"></a>Sous-réseau

Sous-réseaux IP de couche 3 fournissent un mécanisme pris en charge par tous les Skype pour les clients Business Server qui peuvent être utilisés pour détecter automatiquement emplacement du client. L’utilisation de sous-réseaux IP constitue la méthode d’emplacement la plus simple pour configurer et gérer des clients câblés. Avant d’opter pour l’utilisation de sous-réseaux, en revanche, répondez aux questions suivantes pour déterminer si la spécificité de l’emplacement du sous-réseau est suffisamment fine pour rechercher un client avec précision :
  
- Un ou plusieurs sous-réseaux des clients couvrent-ils plusieurs étages ?
    
- Un ou plusieurs sous-réseaux couvrent-t-ils plusieurs immeubles ?
    
- Quelle est la surface couverte par chaque sous-réseau client ?
    
Si le sous-réseau couvre une zone trop vaste, vous devrez envisager d’utiliser un autre mécanisme pour rechercher les clients. Cependant, si possible, nous recommandons aux clients de réorganiser leur sous-réseau IP afin de respecter les exigences de spécificité d’emplacement ERL plutôt que d’induire le coût et la complexité des solutions SNMP tierces.
  
## <a name="client-mac-address"></a>Adresse MAC d’un client

Pour utiliser l’adresse MAC de l’ordinateur client pour localiser un appelant, vous devez les commutateurs Ethernet gérés, et vous devez déployer une solution SNMP tiers qui peut découvrir les adresses MAC de Skype pour les clients professionnels connectés à (ou via) les commutateurs. La solution SNMP interroge continuellement les commutateurs gérés pour obtenir les mappages actuels des adresses MAC de point de terminaison connectées à chaque port et obtient les IP de port correspondants. Pendant une Skype pour demande de clients au service informations d’emplacement, le service informations d’emplacement interroge l’application tierce à l’aide de l’adresse du client MAC, puis renvoie des adresses IP de commutateur correspondantes et des ID de port. Le service informations d’emplacement utilise ces informations pour interroger le schéma de câblage couche 2 publié pour correspondre à un enregistrement et renvoie l’emplacement pour le client. Si vous utilisez cette option, vérifiez que les identifiants de port de commutateur sont cohérents entre l’application SNMP et les enregistrements de la base de données d’emplacements publiés.
  
> [!NOTE]
> Certaines solutions de SNMP tiers peuvent prendre en charge les commutateurs d’accès non managé ; Si le commutateur que les services du Skype pour client d’entreprise n’est pas géré mais a une liaison à un commutateur de distribution gérées, le commutateur géré permettre compte-rendu à l’application SNMP les adresses MAC des clients connectés au commutateur access. Ces informations permettent le service informations d’emplacement identifier l’emplacement de l’utilisateur. Cependant, il est possible d’affecter un seul ERL à tous les ports sur le commutateur non géré afin que la spécificité de l’emplacement soit disponible uniquement au niveau du châssis du commutateur d’accès, et non au niveau du port. 
  

