---
title: Gestion des emplacements pour les fournisseurs de services de jonction SIP (Session Initiation Protocol) dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: Décisions nécessaires pour planifier une la base de données d’informations ou une base de données externe similaire, pour un déploiement E9-1-1 à l’aide de fournisseurs d’acheminement SIP dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 61aec2a537a9351c73c9e1e903685f686d500517
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server-2015"></a>Gestion des emplacements pour les fournisseurs de services de jonction SIP (Session Initiation Protocol) dans Skype Entreprise Server 2015
 
Décisions nécessaires pour planifier une la base de données d’informations ou une base de données externe similaire, pour un déploiement E9-1-1 à l’aide de fournisseurs d’acheminement SIP dans Skype pour Business Server Enterprise Voice.
  
Pour configurer Skype pour Business Server détecte automatiquement les clients au sein d’un réseau, vous devez remplir la base de données du service informations d’emplacement avec un schéma de câblage réseau et les emplacements de publication, soit lien vers une base de données externe qui contient déjà les mappages corrects. Dans le cadre de ce processus, vous devez valider les adresses géographiques des emplacements avec votre fournisseur de services E9-1-1. Pour plus d’informations, voir [Configure the Location Database](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) dans la documentation de déploiement.
  
Renseignez la base de données du service Informations d’emplacement avec un emplacement d’intervention d’urgence (ERL), composé d’une adresse géographique et de l’adresse spécifique au sein d’un bâtiment. Le champ **d’emplacement** de service informations d’emplacement, qui est l’emplacement spécifique dans un bâtiment, a une longueur maximale de 20 caractères (espaces compris). En respectant cette limite, essayez d’inclure les éléments suivants :
  
- Nom facile à comprendre qui identifie l’emplacement de l’appelant 911 pour s’assurer que les agents des services d’urgence trouvent l’emplacement spécifique rapidement lorsqu’ils arrivent à l’adresse géographique. Ce nom d’emplacement peut inclure un numéro d’immeuble, un numéro d’étage, un indicateur d’aile, un numéro de chambre, etc. Évitez les surnoms connus des seuls employés, qui peuvent induire les agents des services d’urgence en erreur.
    
- Un identificateur d’emplacement qui permet aux utilisateurs de voir facilement que leur Skype pour client Business choisie à l’emplacement correct. Le Skype pour client Business concaténé automatiquement et affiche les champs **emplacement** et **ville** découverts dans son en-tête. Une bonne pratique consiste à ajouter l’adresse postale du bâtiment à l’identificateur de chaque emplacement (par exemple, « 1er étage <street number>»). Sans l’adresse postale, un identificateur d’emplacement générique tel que « 1er étage » peut s’appliquer à n’importe quel immeuble de la ville.
    
- Si l’emplacement est approximatif car il est déterminé par un point d’accès sans fil, vous pouvez ajouter le mot **[près]** (par exemple, « proximité du 1er étage 1234 »).
    
> [!NOTE]
> Emplacements ajoutés à la base de données centrale ne sont pas disponibles pour le client jusqu'à ce qu’ils sont publiés à l’aide d’un Skype pour commande Business Server Management Shell et répliqués dans les magasins locaux du pool. Pour plus d’informations, voir [la base de données de l’emplacement de publication](http://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) dans la documentation de déploiement.
  
Les sections suivantes abordent les points à prendre en considération lorsque vous remplissez et mettez à jour la base de données des emplacements.
  
## <a name="populating-the-location-database"></a>Remplissage de la base de données d’emplacements

Les questions suivantes vous permettront de déterminer comment remplir la base de données des emplacements.
  
 **Quel processus allez-vous adopter pour remplir la base de données d’emplacements ?**
  
Où sont stockées les données et quelles étapes devez-vous suivre pour les convertir au format requis par la base de données d’emplacements ? Allez-vous ajouter des emplacements individuellement ou en bloc en utilisant un fichier CSV ? 
  
 **Disposez-vous d’une base de données tierce qui contient déjà un mappage des emplacements ?**
  
À l’aide de l’option de service informations d’emplacement secondaire pour se connecter à une base de données tiers, vous pouvez regrouper et gérer les emplacements à l’aide d’une plate-forme en mode hors connexion. Outre la possibilité d’associer des emplacements à des identificateurs réseau, cette approche vous offre l’avantage d’associer des emplacements à un utilisateur. Cela signifie que le service informations d’emplacement peut retourner plusieurs adresses, provenant du service informations d’emplacement secondaire, à un Skype pour client d’entreprise. L’utilisateur peut alors choisir l’emplacement le plus approprié. 
  
Pour intégrer avec le service informations d’emplacement, la base de données de tiers doit respecter le schéma de Lync Server emplacement demande/réponse. Pour plus d’informations, voir [» [MS-E911WS] : Service Web pour la spécification du protocole E911 prise en charge »](https://go.microsoft.com/fwlink/p/?linkid=213819). Pour plus d’informations sur le déploiement d’un service informations d’emplacement secondaire, voir [configurer un service d’informations d’emplacement secondaire dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) dans la documentation de déploiement.
  
Pour plus d’informations sur le renseignement de la base de données d’emplacement, voir [Configure the Location Database](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) dans la documentation de déploiement.
  
## <a name="maintaining-the-location-database"></a>Mise à jour de la base de données d’emplacements

Une fois que vous avez renseigné la base de données des emplacements, vous devez développer une stratégie pour la mettre à jour au fur et à mesure que la configuration réseau change. Les questions suivantes vous permettront de déterminer comment maintenir la base de données des emplacements.
  
 **Comment allez-vous mettre à jour la base de données d’emplacements ?**
  
L’ajout de points d’accès sans fil, le recâblage du bureau (qui implique des affectations de commutateur différentes) et l’extension des sous-réseaux font partie des nombreux scénarios qui requièrent la mise à jour de la base de données des emplacements. Mettrez-vous directement à jour chaque emplacement individuel ou effectuerez-vous une mise à jour en bloc de tous les emplacements en utilisant un fichier CSV ?
  
 **Ferez-vous appel à une application SNMP pour associer des adresses MAC de client Lync aux identificateurs de port et de commutateur ?**
  
Si vous utilisez une application SNMP, vous devez développer un processus manuel permettant de garder les informations de châssis de commutateur et de port cohérentes entre l’application SNMP et la base de données des emplacements. Si l’application SNMP renvoie un ID d’IP châssis adresse ou un port qui n’est pas inclus dans la base de données, le service informations d’emplacement ne sera pas en mesure de retourner un emplacement pour le client.
  

