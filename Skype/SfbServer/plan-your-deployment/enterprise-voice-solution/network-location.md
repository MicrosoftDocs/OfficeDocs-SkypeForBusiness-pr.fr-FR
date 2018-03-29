---
title: Définition des éléments réseau utilisés pour déterminer l’emplacement dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: Décisions nécessaires à la planification des composants réseau que vous allez utiliser pour mapper les appelants à des emplacements pour le déploiement de E9-1-1 dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 2d371b2abfd8e3c871f0d9f49409d2b8169268c2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server-2015"></a>Définition des éléments réseau utilisés pour déterminer l’emplacement dans Skype Entreprise Server 2015
 
Décisions nécessaires à la planification des composants réseau que vous allez utiliser pour mapper les appelants à des emplacements pour le déploiement de E9-1-1 dans Skype pour Business Server Voix Entreprise.
  
Si vous configurez votre Skype pour infrastructure de serveur d’entreprise pour prendre en charge la détection automatique des clients de l’emplacement, vous devez d’abord décider quel réseau éléments que vous vous apprêtez à utiliser pour mapper les appelants aux emplacements. Dans Skype pour Business Server, vous pouvez associer les éléments de réseau de couche 2 et couche 3 suivants emplacements :
  
- Adresses BSSID (Basic Service Set Identification) des points d’accès sans fil (WAP) (couche 2)
    
- Port commuté LLDP (couche 2)
    
- ID de châssis commuté LLDP (couche 2)
    
- Sous-réseaux IP (couche 3)
    
- Adresses MAC des clients (couche 2)
    
Les éléments réseau sont répertoriés par ordre de priorité. Si un client peut se trouver à l’aide de plus d’un élément réseau, Skype pour Business Server utilise l’ordre de priorité pour déterminer quel mécanisme à utiliser. 
  
Les sections suivantes abordent plus en détail l’utilisation de chaque élément réseau.
  
> [!IMPORTANT]
> Lorsque vous utilisez des éléments de réseau pour mapper les appelants à des emplacements, il est d’une importance capitale de conserver la base de données du service de coordonnées à jour. Par exemple, si vous ajoutez ou modifiez un élément réseau, comme un point d’accès sans fil, vous devez supprimer l’ancienne entrée et ajouter la nouvelle entrée dans la base de données d’emplacements. 
  
## <a name="wireless-access-point"></a>Point d’accès sans fil

Lorsqu’un client se connecte au réseau via une liaison sans fil, la demande d’emplacement utilise l’adresse BSSID du point d’accès sans fil pour déterminer son emplacement. Si le client est en itinérance, le WAP indiqué peut ne pas être celui le plus proche, et il est même possible de chercher un point d’accès qui se trouve sur un autre étage du bâtiment. Pour indiquer que l’emplacement est approximative, vous pouvez ajouter la valeur de l’emplacement avec un descripteur de **[près]** ou **[Fermer pour]** .
  
Cette méthode d’emplacement part du principe que le BSSID de chaque point d’accès sans fil est statique. Toutefois, si le fournisseur de votre WAP utilise affectées de manière dynamique les BSSID, le BSSID est obtenu à partir d’un point d’accès pourrait modifier (qui peut se produire suite à une modification de configuration WAP) et les clients sans fil peuvent se retrouver dans une situation où ils ne reçoivent pas un emplacement. Pour éviter cette possibilité, vous devez remplir l’informations d’emplacement service base de données avec ERLs pour toutes les adresses BSSID possibles utilisé par chaque WAP. 
  
## <a name="lldp-ports-and-switches"></a>Ports et commutateurs LLDP

Les commutateurs Ethernet gérés qui prennent en charge le protocole LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) peuvent annoncer leur identité et leurs informations de port aux clients compatibles LLDP-MED, lesquelles peuvent alors faire l’objet d’une requête dans la base de données d’emplacements afin de fournir l’emplacement du périphérique. Vous pouvez associer des ERL uniquement sur l’ID du châssis commuté, ou les mapper au niveau du port.
  
> [!NOTE]
> Skype pour Business Server prend en charge l’utilisation LLDP-MED pour déterminer les emplacements uniquement de périphériques Lync Phone Edition et Skype pour les clients d’entreprise s’exécutant sur Windows 8. Si vous avez besoin d’utiliser des données de couche 2 au niveau du switch pour déterminer l’emplacement des autre Skype sur PC filaire pour clients Business Server, vous devez utiliser la méthode d’adresse MAC du client. 
  
## <a name="subnet"></a>Sous-réseau

Sous-réseaux IP de couche 3 fournissent un mécanisme pris en charge par tous les Skype pour les clients Business Server qui peuvent être utilisés pour détecter automatiquement l’emplacement client. L’utilisation de sous-réseaux IP constitue la méthode d’emplacement la plus simple pour configurer et gérer des clients câblés. Avant d’opter pour l’utilisation de sous-réseaux, en revanche, répondez aux questions suivantes pour déterminer si la spécificité de l’emplacement du sous-réseau est suffisamment fine pour rechercher un client avec précision :
  
- Un ou plusieurs sous-réseaux des clients couvrent-ils plusieurs étages ?
    
- Un ou plusieurs sous-réseaux couvrent-t-ils plusieurs immeubles ?
    
- Quelle est la surface couverte par chaque sous-réseau client ?
    
Si le sous-réseau couvre une zone trop vaste, vous devrez envisager d’utiliser un autre mécanisme pour rechercher les clients. Cependant, si possible, nous recommandons aux clients de réorganiser leur sous-réseau IP afin de respecter les exigences de spécificité d’emplacement ERL plutôt que d’induire le coût et la complexité des solutions SNMP tierces.
  
## <a name="client-mac-address"></a>Adresse MAC d’un client

Pour utiliser l’adresse MAC de l’ordinateur client pour localiser un appelant, vous devez les commutateurs Ethernet, et vous devez déployer une solution SNMP tiers qui découvrira les adresses MAC de Skype pour les clients d’entreprise connectés à (ou via) des commutateurs. La solution SNMP interroge continuellement les commutateurs gérés pour obtenir les mappages actuels des adresses MAC de point de terminaison connectées à chaque port et obtient les IP de port correspondants. Pendant un Skype pour la demande des clients pour le service d’informations d’emplacement, le service d’informations d’emplacement l’application tierce à l’aide de l’adresse du client MAC et puis retourne tout commutateur correspondant des adresses IP et les ID de port. Le service d’informations d’emplacement utilise ces informations pour son wiremap de couche 2 publié pour correspondre à un enregistrement de la requête et renvoie l’emplacement du client. Si vous utilisez cette option, vérifiez que les identifiants de port de commutateur sont cohérents entre l’application SNMP et les enregistrements de la base de données d’emplacements publiés.
  
> [!NOTE]
> Certaines solutions SNMP tiers peuvent prendre en charge les commutateurs d’accès non managé ; Si le commutateur qui dessert la Skype pour client d’entreprise n’est pas géré, mais a une liaison montante vers un commutateur géré de distribution, le commutateur géré peut notifier à l’application SNMP les adresses MAC des clients connectés au commutateur d’accès. Ces informations permettent le service d’informations d’emplacement identifier l’emplacement de l’utilisateur. Cependant, il est possible d’affecter un seul ERL à tous les ports sur le commutateur non géré afin que la spécificité de l’emplacement soit disponible uniquement au niveau du châssis du commutateur d’accès, et non au niveau du port. 
  

