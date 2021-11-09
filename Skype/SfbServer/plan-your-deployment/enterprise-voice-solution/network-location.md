---
title: Définir les éléments réseau utilisés pour déterminer l’emplacement dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: Décisions nécessaires à la planification des composants réseau que vous utiliserez pour ma cartographier les appelants à des emplacements pour le déploiement E9-1-1 dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 6de3d960dd68dfc0f34ce0e67fef569c36e44612
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861111"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>Définir les éléments réseau utilisés pour déterminer l’emplacement dans Skype Entreprise Server
 
Décisions nécessaires à la planification des composants réseau que vous utiliserez pour ma cartographier les appelants à des emplacements pour le déploiement E9-1-1 dans Skype Entreprise Server Voix Entreprise.
  
Si vous programmez la configuration de votre infrastructure Skype Entreprise Server pour prendre en charge la détection automatique de l’emplacement du client, vous devez d’abord déterminer les éléments réseau que vous allez utiliser pour ma map trancher les appelants avec les emplacements. Dans Skype Entreprise Server, vous pouvez associer les éléments réseau de couche 2 et 3 suivants à des emplacements :
  
- Adresses BSSID (Basic Service Set Identification) des points d’accès sans fil (WAP) (couche 2)
    
- Port commuté LLDP (couche 2)
    
- ID de châssis commuté LLDP (couche 2)
    
- Sous-réseaux IP (couche 3)
    
- Adresses MAC des clients (couche 2)
    
Les éléments réseau sont répertoriés par ordre de priorité. Si un client peut être localisé à l’aide de plusieurs éléments réseau, Skype Entreprise Server utilise l’ordre de priorité pour déterminer le mécanisme à utiliser. 
  
Les sections suivantes abordent plus en détail l’utilisation de chaque élément réseau.
  
> [!IMPORTANT]
> Lorsque vous utilisez des éléments réseau pour ma router des appelants vers des emplacements, il est très important de maintenir la base de données du service Informations sur l’emplacement à jour. Par exemple, si vous ajoutez ou modifiez un élément réseau, comme un point d’accès sans fil, vous devez supprimer l’ancienne entrée et ajouter la nouvelle entrée dans la base de données d’emplacements. 
  
## <a name="wireless-access-point"></a>Point d’accès sans fil

Lorsqu’un client se connecte au réseau via une liaison sans fil, la demande d’emplacement utilise l’adresse BSSID du point d’accès sans fil pour déterminer son emplacement. Si le client est en itinérance, le point d’accès sans accès indiqué n’est peut-être pas le plus proche et il est même possible de récupérer un point d’accès sans accès qui se trouve à un autre étage du bâtiment. Pour indiquer que l’emplacement est approximatif, vous pouvez faire précéder la valeur de l’emplacement par un descripteur **[Near]** ou **[Closeto].**
  
Cette méthode d’emplacement part du principe que le BSSID de chaque point d’accès sans fil est statique. Toutefois, si votre fournisseur de point d’accès sans fil utilise des BSSID affectés dynamiquement, le BSSID obtenu à partir d’un point d’accès sans fil peut changer (cela peut se produire suite à un changement de configuration du point d’accès sans fil) et les clients sans fil peuvent se trouver dans une situation où ils ne reçoivent pas d’emplacement. Pour éviter cette possibilité, vous devez remplir la base de données du service Informations d’emplacement avec des ERL pour toutes les adresses BSSID possibles utilisées par chaque fournisseur d’accès sans accès sans accès. 
  
## <a name="lldp-ports-and-switches"></a>Ports et commutateurs LLDP

Les commutateurs Ethernet gérés qui prennent en charge le protocole LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) peuvent annoncer leur identité et leurs informations de port aux clients compatibles LLDP-MED, lesquelles peuvent alors faire l’objet d’une requête dans la base de données d’emplacements afin de fournir l’emplacement du périphérique. Vous pouvez associer des ERL uniquement sur l’ID du châssis commuté, ou les mapper au niveau du port.
  
> [!NOTE]
> Skype Entreprise Server prend en charge l’utilisation de LLDP-MED pour déterminer uniquement les emplacements des appareils Lync Téléphone Edition et des clients Skype Entreprise s’exécutant sur Windows 8. Si vous devez utiliser des données de couche de niveau commutateur 2 pour déterminer l’emplacement d’autres clients Skype Entreprise Server PC câblés, vous devez utiliser la méthode d’adresse MAC cliente. 
  
## <a name="subnet"></a>Sous-réseau

Les sous-réseaux IP de couche 3 fournissent un mécanisme pris en charge par tous Skype Entreprise Server clients qui peuvent être utilisés pour détecter automatiquement l’emplacement du client. L’utilisation de sous-réseaux IP constitue la méthode d’emplacement la plus simple pour configurer et gérer des clients câblés. Avant d’opter pour l’utilisation de sous-réseaux, en revanche, répondez aux questions suivantes pour déterminer si la spécificité de l’emplacement du sous-réseau est suffisamment fine pour localiser un client avec précision :
  
- Un ou plusieurs sous-réseaux des clients couvrent-ils plusieurs étages ?
    
- Un ou plusieurs sous-réseaux couvrent-t-ils plusieurs immeubles ?
    
- Quelle est la surface couverte par chaque sous-réseau client ?
    
Si le sous-réseau couvre une zone trop vaste, vous devrez envisager d’utiliser un autre mécanisme pour localiser les clients. Toutefois, si possible, nous recommandons aux clients de réorganiser leur sous-réseau IP afin de respecter les exigences de spécificité d’emplacement ERL plutôt que d’induire le coût et la complexité des solutions SNMP tierces.
  
## <a name="client-mac-address"></a>Adresse MAC d’un client

Pour utiliser l’adresse MAC d’un ordinateur client pour localiser un appelant, vous avez besoin de commutateurs Ethernet gérés et vous devez déployer une solution SNMP tierce qui peut découvrir les adresses MAC des clients Skype Entreprise connectés à (ou via) ces commutateurs. La solution SNMP interroge continuellement les commutateurs gérés pour obtenir les mappages actuels des adresses MAC de point de terminaison connectées à chaque port et obtient les IP de port correspondants. Lors de la demande d’un client Skype Entreprise au service Informations d’emplacement, le service Informations d’emplacement interroge l’application tierce à l’aide de l’adresse MAC du client, puis renvoie les adresses IP de commutateur et les ID de port correspondants. Le service Informations sur l’emplacement utilise ces informations pour interroger son plan de câblage de couche 2 publié pour obtenir un enregistrement correspondant et renvoie l’emplacement au client. Si vous utilisez cette option, vérifiez que les identifiants de port de commutateur sont cohérents entre l’application SNMP et les enregistrements de la base de données d’emplacements publiés.
  
> [!NOTE]
> Certaines solutions SNMP tierces peuvent prendre en charge les commutateurs d’accès nonmanagés ; Si le commutateur qui prend en charge le client Skype Entreprise n’est pas géré mais possède un lien vers un commutateur de distribution géré, le commutateur géré peut signaler à l’application SNMP les adresses MAC des clients connectés au commutateur d’accès. Ces informations permettent au service Informations d’emplacement d’identifier l’emplacement de l’utilisateur. Toutefois, il est possible d’affecter un seul ERL à tous les ports sur le commutateur non géré, afin que la spécificité de l’emplacement soit disponible uniquement au niveau du châssis du commutateur d’accès, et non au niveau du port. 
  

