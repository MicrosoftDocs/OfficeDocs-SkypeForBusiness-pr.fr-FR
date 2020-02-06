---
title: Définir les éléments réseau utilisés pour déterminer l’emplacement dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: Les décisions nécessaires pour planifier les composants réseau que vous allez utiliser pour mapper les appelants vers des emplacements pour le déploiement de E9-1-1 dans Skype entreprise Server Voice.
ms.openlocfilehash: 404ac2d151f367ad391e4d5426090f20448cc383
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802664"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>Définir les éléments réseau utilisés pour déterminer l’emplacement dans Skype entreprise Server
 
Les décisions nécessaires pour planifier les composants réseau que vous allez utiliser pour mapper les appelants vers des emplacements pour le déploiement de E9-1-1 dans Skype entreprise Server Voice.
  
Si vous configurez votre infrastructure du serveur Skype entreprise pour prendre en charge la détection automatique de l’emplacement du client, vous devez d’abord choisir les éléments réseau que vous allez utiliser pour mapper les appelants vers des emplacements. Dans Skype entreprise Server, vous pouvez associer les éléments réseau Layer 2 et Layer 3 suivants à des emplacements :
  
- Adresses BSSID (Basic Service Set Identification) des points d’accès sans fil (WAP) (couche 2)
    
- Port commuté LLDP (couche 2)
    
- ID de châssis commuté LLDP (couche 2)
    
- Sous-réseaux IP (couche 3)
    
- Adresses MAC des clients (couche 2)
    
Les éléments réseau sont répertoriés par ordre de priorité. Si un client peut être localisé à l’aide de plusieurs éléments réseau, Skype entreprise Server utilise l’ordre de priorité pour déterminer le mécanisme à utiliser. 
  
Les sections suivantes abordent plus en détail l’utilisation de chaque élément réseau.
  
> [!IMPORTANT]
> Lorsque vous utilisez des éléments réseau pour mapper les appelants aux emplacements, il est très important que vous maintienez la base de données de service des informations d’emplacement à jour. Par exemple, si vous ajoutez ou modifiez un élément réseau, comme un point d’accès sans fil, vous devez supprimer l’ancienne entrée et ajouter la nouvelle entrée dans la base de données d’emplacements. 
  
## <a name="wireless-access-point"></a>Point d’accès sans fil

Lorsqu’un client se connecte au réseau via une liaison sans fil, la demande d’emplacement utilise l’adresse BSSID du point d’accès sans fil pour déterminer son emplacement. Si le client est en itinérance, le WAP indiqué peut ne pas être le plus proche, et il est même possible de décrocher un WAP sur un étage différent du bâtiment. Pour indiquer que l’emplacement est approximatif, vous pouvez faire précéder la valeur de l’emplacement d’un descripteur **[near]** ou **[armoireo]** .
  
Cette méthode d’emplacement part du principe que le BSSID de chaque point d’accès sans fil est statique. Toutefois, si votre fournisseur de WAP utilise BSSIDs de manière dynamique, le BSSID obtenu à partir d’un WAP peut changer (cela peut se produire suite à une modification de configuration de WAP), et les clients sans fil peuvent être laissés dans une situation où ils ne reçoivent aucun emplacement. Pour éviter ce problème, vous devez remplir la base de données de service informations d’emplacement avec ERLs pour toutes les adresses BSSID possibles utilisées par chaque WAP. 
  
## <a name="lldp-ports-and-switches"></a>Ports et commutateurs LLDP

Les commutateurs Ethernet gérés qui prennent en charge le protocole LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) peuvent annoncer leur identité et leurs informations de port aux clients compatibles LLDP-MED, lesquelles peuvent alors faire l’objet d’une requête dans la base de données d’emplacements afin de fournir l’emplacement du périphérique. Vous pouvez associer des ERL uniquement sur l’ID du châssis commuté, ou les mapper au niveau du port.
  
> [!NOTE]
> Skype entreprise Server prend en charge l’utilisation de LLDP-MED pour déterminer les emplacements uniquement des appareils Lync Phone Edition et Skype entreprise s’exécutant sur Windows 8. Si vous avez besoin d’utiliser des données de couche 2 de niveau commutateur pour déterminer l’emplacement d’autres clients câblés de Skype entreprise sur un PC, vous devez utiliser la méthode d’adresse MAC du client. 
  
## <a name="subnet"></a>Sous-réseau

Les sous-réseaux IP de Layer 3 fournissent un mécanisme pris en charge par tous les clients Skype entreprise Server qui peuvent être utilisés pour détecter automatiquement l’emplacement du client. L’utilisation de sous-réseaux IP constitue la méthode d’emplacement la plus simple pour configurer et gérer des clients câblés. Avant d’opter pour l’utilisation de sous-réseaux, en revanche, répondez aux questions suivantes pour déterminer si la spécificité de l’emplacement du sous-réseau est suffisamment fine pour rechercher un client avec précision :
  
- Un ou plusieurs sous-réseaux des clients couvrent-ils plusieurs étages ?
    
- Un ou plusieurs sous-réseaux couvrent-t-ils plusieurs immeubles ?
    
- Quelle est la surface couverte par chaque sous-réseau client ?
    
Si le sous-réseau couvre une zone trop vaste, vous devrez envisager d’utiliser un autre mécanisme pour rechercher les clients. Cependant, si possible, nous recommandons aux clients de réorganiser leur sous-réseau IP afin de respecter les exigences de spécificité d’emplacement ERL plutôt que d’induire le coût et la complexité des solutions SNMP tierces.
  
## <a name="client-mac-address"></a>Adresse MAC d’un client

Pour utiliser l’adresse MAC d’un ordinateur client pour localiser un appelant, vous avez besoin de commutateurs Ethernet gérés et vous devez déployer une solution SNMP tierce capable de détecter les adresses MAC des clients Skype entreprise connectés (ou par le biais de) ces commutateurs. La solution SNMP interroge continuellement les commutateurs gérés pour obtenir les mappages actuels des adresses MAC de point de terminaison connectées à chaque port et obtient les IP de port correspondants. Dans le cadre d’une demande de client Skype entreprise adressée au service d’information d’emplacement, le service d’information d’emplacement interroge l’application tierce en utilisant l’adresse MAC du client, puis renvoie les adresses IP et ID de port correspondants. Le service des informations d’emplacement utilise ces informations pour interroger son Wiremap Layer 2 publié pour un enregistrement de correspondance et renvoie l’emplacement au client. Si vous utilisez cette option, vérifiez que les identifiants de port de commutateur sont cohérents entre l’application SNMP et les enregistrements de la base de données d’emplacements publiés.
  
> [!NOTE]
> Certaines solutions SNMP tierces peuvent prendre en charge des commutateurs d’accès non gérés ; Si le commutateur de services Skype entreprise n’est pas géré par le client et qu’il dispose d’un lien vers un commutateur de distribution géré, le commutateur géré peut signaler à l’application SNMP les adresses MAC des clients connectés au commutateur d’accès. Ces informations permettent au service d’information d’emplacement d’identifier l’emplacement de l’utilisateur. Cependant, il est possible d’affecter un seul ERL à tous les ports sur le commutateur non géré afin que la spécificité de l’emplacement soit disponible uniquement au niveau du châssis du commutateur d’accès, et non au niveau du port. 
  

