---
title: Gestion des emplacements pour les fournisseurs de services de jonction SIP (Session Initiation Protocol) dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: Les décisions nécessaires à la planification une la base de données des informations d’emplacement, ou une base de données externe similaire, pour un déploiement E9-1-1 à l’aide de fournisseurs de trunking SIP dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: e4337a6aaa37a7105b5ab9fbbcc8242237a6954c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server-2015"></a>Gestion des emplacements pour les fournisseurs de services de jonction SIP (Session Initiation Protocol) dans Skype Entreprise Server 2015
 
Les décisions nécessaires à la planification une la base de données des informations d’emplacement, ou une base de données externe similaire, pour un déploiement E9-1-1 à l’aide de fournisseurs de trunking SIP dans Skype pour Business Server Voix Entreprise.
  
Pour configurer Skype pour Business Server détecte automatiquement les clients au sein d’un réseau, vous devez remplir la base de données de service d’informations d’emplacement avec un wiremap de réseau et les emplacements de publication, soit créer un lien vers une base de données externe qui contient déjà des les mappages corrects. Dans le cadre de ce processus, vous devez valider les adresses géographiques des emplacements avec votre fournisseur de services E9-1-1. Pour plus d’informations, consultez [configurer la base de données d’emplacement](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) dans la documentation de déploiement.
  
Renseignez la base de données du service Informations d’emplacement avec un emplacement d’intervention d’urgence (ERL), composé d’une adresse géographique et de l’adresse spécifique au sein d’un bâtiment. Le champ **d’emplacement** de service informations d’emplacement, qui est l’emplacement spécifique au sein d’un bâtiment, a une longueur maximale de 20 caractères (espaces compris). En respectant cette limite, essayez d’inclure les éléments suivants :
  
- Nom facile à comprendre qui identifie l’emplacement de l’appelant 911 pour s’assurer que les agents des services d’urgence trouvent l’emplacement spécifique rapidement lorsqu’ils arrivent à l’adresse géographique. Ce nom d’emplacement peut inclure un numéro d’immeuble, un numéro d’étage, un indicateur d’aile, un numéro de chambre, etc. Évitez les surnoms connus des seuls employés, qui peuvent induire les agents des services d’urgence en erreur.
    
- Un identificateur qui permet aux utilisateurs de voir facilement que leur Skype pour client d’entreprise chercher l’emplacement correct. Le Skype pour client d’entreprise concatène automatiquement et affiche les champs **emplacement** et **ville** découverts dans son en-tête. Une bonne pratique consiste à ajouter de l’adresse postale du bâtiment pour chaque identificateur d’emplacement (par exemple, « 1 st Floor <street number>»). Sans l’adresse postale, un identificateur d’emplacement générique tel que « 1er étage » peut s’appliquer à n’importe quel immeuble de la ville.
    
- Si l’emplacement est approximative, car elle est déterminée par un point d’accès sans fil, vous pouvez ajouter le mot **[en]** (par exemple, « à côté de 1er étage 1234 »).
    
> [!NOTE]
> Ajouté à la base de données de l’emplacement central des emplacements ne sont pas disponibles pour le client jusqu'à ce qu’ils sont publiés à l’aide d’un Skype pour commande Business Server Management Shell sont répliqués dans les magasins locaux du pool. Pour plus d’informations, consultez [la base de données de l’emplacement de publication](http://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) dans la documentation de déploiement.
  
Les sections suivantes abordent les points à prendre en considération lorsque vous remplissez et mettez à jour la base de données des emplacements.
  
## <a name="populating-the-location-database"></a>Remplissage de la base de données d’emplacements

Les questions suivantes vous permettront de déterminer comment remplir la base de données des emplacements.
  
 **Quel processus allez-vous adopter pour remplir la base de données d’emplacements ?**
  
Où sont stockées les données et quelles étapes devez-vous suivre pour les convertir au format requis par la base de données d’emplacements ? Allez-vous ajouter des emplacements individuellement ou en bloc en utilisant un fichier CSV ? 
  
 **Disposez-vous d’une base de données tierce qui contient déjà un mappage des emplacements ?**
  
À l’aide de l’option de service d’informations sur l’emplacement secondaire pour se connecter à une base de données tierce, vous pouvez regrouper et gérer des emplacements à l’aide d’une plate-forme en mode hors connexion. Outre la possibilité d’associer des emplacements à des identificateurs réseau, cette approche vous offre l’avantage d’associer des emplacements à un utilisateur. Cela signifie que le service d’informations d’emplacement peut retourner plusieurs adresses, à partir du service d’informations sur l’emplacement secondaire, d’origine à un Skype pour client d’entreprise. L’utilisateur peut alors choisir l’emplacement le plus approprié. 
  
Pour intégrer avec le service d’informations sur l’emplacement, la base de données tierce doit respecter le schéma demande/réponse de Lync Server emplacement. Pour plus d’informations, consultez [» [MS-E911WS] : Service Web pour la spécification de protocole de prise en charge E911 »](https://go.microsoft.com/fwlink/p/?linkid=213819). Pour plus d’informations sur le déploiement d’un service d’informations sur l’emplacement secondaire, consultez [configurer un service d’informations sur l’emplacement secondaire dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) dans la documentation de déploiement.
  
Pour plus d’informations sur le remplissage de la base de données de l’emplacement, consultez [configurer la base de données d’emplacement](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) dans la documentation de déploiement.
  
## <a name="maintaining-the-location-database"></a>Mise à jour de la base de données d’emplacements

Une fois que vous avez renseigné la base de données des emplacements, vous devez développer une stratégie pour la mettre à jour au fur et à mesure que la configuration réseau change. Les questions suivantes vous permettront de déterminer comment maintenir la base de données des emplacements.
  
 **Comment allez-vous mettre à jour la base de données d’emplacements ?**
  
L’ajout de points d’accès sans fil, le recâblage du bureau (qui implique des affectations de commutateur différentes) et l’extension des sous-réseaux font partie des nombreux scénarios qui requièrent la mise à jour de la base de données des emplacements. Mettrez-vous directement à jour chaque emplacement individuel ou effectuerez-vous une mise à jour en bloc de tous les emplacements en utilisant un fichier CSV ?
  
 **Ferez-vous appel à une application SNMP pour associer des adresses MAC de client Lync aux identificateurs de port et de commutateur ?**
  
Si vous utilisez une application SNMP, vous devez développer un processus manuel permettant de garder les informations de châssis de commutateur et de port cohérentes entre l’application SNMP et la base de données des emplacements. Si l’application SNMP renvoie un ID d’IP châssis adresse ou un port qui n’est pas inclus dans la base de données, le service d’informations d’emplacement ne sera pas en mesure de retourner un emplacement pour le client.
  

