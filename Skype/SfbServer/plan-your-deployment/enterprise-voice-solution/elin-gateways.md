---
title: Gérer les emplacements pour les passerelles ELIN dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: Décisions nécessaires pour planifier une la base de données d’informations ou une base de données externe similaire, pour un déploiement E9-1-1 dans les passerelles ELIN, Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 09397c84e69ee9df2c40bd1783c8f57a58aa21d4
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252918"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a>Gérer les emplacements pour les passerelles ELIN dans Skype pour Business Server

Décisions nécessaires pour planifier une la base de données d’informations ou une base de données externe similaire, pour un déploiement E9-1-1 dans les passerelles ELIN, Skype pour Business Server Enterprise Voice.

Pour que Skype pour Business Server fournisse automatiquement les emplacements pour les clients au sein d’un réseau, vous devez effectuer les tâches suivantes :

- Remplir la base de données du service informations d’emplacement avec un schéma de câblage réseau et incluez les numéros d’Identification d’urgence emplacement (en cas) dans le champ CompanyName.

- Publiez les emplacements afin qu’ils soient disponibles pour les clients dans votre réseau.

- Téléchargez les numéros d’identification de l’emplacement en cas d’urgence vers la base de données ALI (Automatic Location Identification) de votre opérateur PSTN.

Pour plus d’informations sur la façon d’effectuer ces tâches, voir [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) dans la documentation de déploiement.

> [!NOTE]
> Emplacements ajoutés à la base de données centrale ne sont pas disponibles pour le client jusqu'à ce qu’ils ont été publiées à l’aide d’un Skype pour commande Business Server Management Shell et répliqués dans les magasins locaux du pool. Pour plus d’informations, voir [la base de données de l’emplacement de publication](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) dans la documentation de déploiement.

Cette section décrit les éléments à prendre en compte lorsque vous prévoyez de mettre à jour ou maintenir la base de données des emplacements.

## <a name="planning-emergency-locations"></a>Planification des emplacements d’urgence

Lorsque vous utilisez les passerelles ELIN, vous remplissez la base de données du service informations d’emplacement avec l’adresse postale, un emplacement spécifique au sein d’un bâtiment et au moins un ELIN pour chaque emplacement. Durant la phase de planification, il est recommandé de décider du nom des emplacements et de l’affectation des numéros d’identification de l’emplacement en cas d’urgence.

### <a name="planning-location-names"></a>Planification des noms d’emplacement

Le champ **d’emplacement** de service informations d’emplacement, qui contient l’emplacement spécifique dans un bâtiment, a une longueur maximale de 20 caractères (espaces compris). En respectant cette limite, essayez d’inclure les éléments suivants :

- Nom facile à comprendre qui identifie l’emplacement de l’appelant 911 pour s’assurer que les agents des services d’urgence trouvent l’emplacement spécifique rapidement lorsqu’ils arrivent à l’adresse géographique. Ce nom d’emplacement peut inclure un numéro d’immeuble, un numéro d’étage, un indicateur d’aile, un numéro de chambre, etc. Évitez les surnoms connus des seuls employés, qui peuvent induire les agents des services d’urgence en erreur.

- Identificateur d’emplacement qui aide les utilisateurs à vérifier que leur client a sélectionné l’emplacement correct. Le Skype pour client Business concaténé automatiquement et affiche les champs **emplacement** et **ville** découverts dans son en-tête. Une bonne pratique consiste à ajouter l’adresse postale du bâtiment à l’identificateur de chaque emplacement (par exemple, « 1er étage <street number>»). Sans l’adresse postale, un identificateur d’emplacement générique tel que « 1er étage » peut s’appliquer à n’importe quel immeuble de la ville.

- Si l’emplacement est approximatif car il est déterminé par un point d’accès sans fil, il pouvez que vous souhaitez ajouter le mot **[près]** (par exemple, « proximité du 1er étage 1234 »).

### <a name="planning-elins"></a>Planification des numéros d’identification de l’emplacement en cas d’urgence (ELIN)

Après avoir déterminé comment diviser l’espace de votre bâtiment en emplacements, vous devez décider du nombre de numéros ELIN à affecter à chaque emplacement. Par exemple, dans un immeuble à plusieurs étages ou multilocatif, différentes zones ERL peuvent être affectées à différentes zones d’urgence. En général, chaque étage d’un immeuble est désigné comme un emplacement. Chaque emplacement se voit alors affecté un ou plusieurs numéros ELIN, utilisés comme numéros d’appel durant un appel d’urgence. Contactez votre opérateur PSTN pour connaître les numéros de téléphone que vous pouvez utiliser pour les numéros ELIN. Le tableau ci-dessous fournit des exemples d’emplacements pour une adresse postale spécifique.

**Exemples d’affectations d’emplacements et de numéros ELIN**

|**Zone de l’immeuble**|**Emplacement**|**ELIN**|
|:-----|:-----|:-----|
|Premier étage  <br/> |1  <br/> |425-555-0100  <br/> |
|Deuxième étage  <br/> |2  <br/> |425-555-0111  <br/> |
|Troisième étage  <br/> |3  <br/> |425-555-0123  <br/> |

Les emplacements définis doivent satisfaire les exigences suivantes :

- être conformes aux réglementations locales et nationales/régionales en termes de surface maximale par emplacement et nombre d’emplacements par adresse postale ;

- être assez spécifiques pour faciliter la localisation de l’appel d’urgence.

## <a name="populating-the-location-database"></a>Remplissage de la base de données d’emplacements

Les questions suivantes vous permettront de déterminer comment remplir la base de données des emplacements.

 **Quel processus allez-vous adopter pour remplir la base de données d’emplacements ?**

Où sont stockées les données et quelles étapes devez-vous suivre pour les convertir au format requis par la base de données d’emplacements ? Allez-vous ajouter des emplacements individuellement ou en bloc en utilisant un fichier CSV ?

 **Disposez-vous d’une base de données tierce qui contient déjà un mappage des emplacements ?**

À l’aide de l’option de service informations d’emplacement secondaire pour se connecter à une base de données tiers, vous pouvez regrouper et gérer les emplacements à l’aide d’une plate-forme en mode hors connexion. Outre la possibilité d’associer des emplacements à des identificateurs réseau, cette approche vous offre l’avantage d’associer des emplacements à un utilisateur. Cela signifie que le service informations d’emplacement peut retourner plusieurs adresses, provenant du service informations d’emplacement secondaire, à un Skype pour client d’entreprise. L’utilisateur peut alors choisir l’emplacement le plus approprié.

Pour intégrer avec le service informations d’emplacement, la base de données de tiers doit respecter le Skype pour le schéma de demande/réponse Business emplacement du serveur. Pour plus d’informations, voir [Service Web pour E911 prise en charge de protocole](https://go.microsoft.com/fwlink/p/?linkid=213819). Pour plus d’informations sur le déploiement d’un service informations d’emplacement secondaire, voir [configurer un service d’informations d’emplacement secondaire dans Skype pour Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) dans la documentation de déploiement.

Pour plus d’informations sur le renseignement de la base de données d’emplacement, voir [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) dans la documentation de déploiement.

## <a name="maintaining-the-location-database"></a>Mise à jour de la base de données d’emplacements

Une fois que vous avez renseigné la base de données des emplacements, vous devez développer une stratégie pour la mettre à jour au fur et à mesure que la configuration réseau change. Les questions suivantes vous permettront de déterminer comment maintenir la base de données des emplacements.

 **Comment allez-vous mettre à jour la base de données d’emplacements ?**

L’ajout de points d’accès sans fil, le recâblage du bureau (qui implique des affectations de commutateur différentes) et l’extension des sous-réseaux font partie des nombreux scénarios qui requièrent la mise à jour de la base de données des emplacements. Mettrez-vous directement à jour chaque emplacement individuel ou effectuerez-vous une mise à jour en bloc de tous les emplacements en utilisant un fichier CSV ?

 **Allez-vous utiliser une application SNMP pour associer Skype pour les adresses MAC de client Business au port et de commutateur des identificateurs ?**

Si vous utilisez une application SNMP, vous devez développer un processus manuel permettant de garder les informations de châssis de commutateur et de port cohérentes entre l’application SNMP et la base de données des emplacements. Si l’application SNMP renvoie un ID d’IP châssis adresse ou un port qui n’est pas inclus dans la base de données, le service informations d’emplacement ne sera pas en mesure de retourner un emplacement pour le client.


