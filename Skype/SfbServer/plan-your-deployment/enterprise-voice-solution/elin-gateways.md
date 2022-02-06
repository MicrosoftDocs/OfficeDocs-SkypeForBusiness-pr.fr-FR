---
title: Gérer les emplacements des passerelles ELIN dans Skype Entreprise Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ms.custom: null
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: 'Décisions nécessaires à la planification d’une base de données d’informations d’emplacement ou d’une base de données externe similaire pour un déploiement E9-1-1 à l’aide de passerelles ELIN, Skype Entreprise Server Voix Entreprise.'
---

# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a>Gérer les emplacements des passerelles ELIN dans Skype Entreprise Server

Décisions nécessaires à la planification d’une base de données d’informations d’emplacement ou d’une base de données externe similaire pour un déploiement E9-1-1 à l’aide de passerelles ELIN, Skype Entreprise Server Voix Entreprise.

Pour que Skype Entreprise Server fournir automatiquement des emplacements pour les clients au sein d’un réseau, vous devez effectuer les tâches suivantes :

- Remplir la base de données du service Informations sur l’emplacement avec une carte fil de câblage réseau et inclure les numéros d’identification d’emplacement d’urgence (ELIN) dans le champ CompanyName.

- Publiez les emplacements afin qu’ils soient disponibles pour les clients dans votre réseau.

- Téléchargez les numéros d’identification de l’emplacement en cas d’urgence vers la base de données ALI (Automatic Location Identification) de votre opérateur RTC.

Pour plus d’informations sur l’exécution de ces tâches, voir [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) dans la documentation de déploiement.

> [!NOTE]
> Les emplacements ajoutés à la base de données centrale des emplacements ne sont pas disponibles pour le client tant qu’ils n’ont pas été publiés à l’aide d’une commande Skype Entreprise Server Management Shell et répliqués dans les magasins locaux du pool. Pour plus d’informations, voir [Publishing the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-location-database) dans la documentation de déploiement.

Cette section décrit les éléments à prendre en compte lorsque vous prévoyez de mettre à jour ou maintenir la base de données des emplacements.

## <a name="planning-emergency-locations"></a>Planification des emplacements d’urgence

Lorsque vous utilisez des passerelles ELIN, vous devez remplir la base de données du service Informations d’emplacement avec l’adresse géographique, un emplacement spécifique dans un bâtiment et au moins un ELIN pour chaque emplacement. Durant la phase de planification, il est recommandé de décider du nom des emplacements et de l’affectation des numéros d’identification de l’emplacement en cas d’urgence.

### <a name="planning-location-names"></a>Planification des noms d’emplacement

Le champ **Emplacement du service** Informations sur l’emplacement, qui contient l’emplacement spécifique dans un bâtiment, a une longueur maximale de 20 caractères (espaces compris). En respectant cette limite, essayez d’inclure les éléments suivants :

- Nom facile à comprendre qui identifie l’emplacement de l’appelant 911 pour s’assurer que les agents des services d’urgence trouvent l’emplacement spécifique rapidement lorsqu’ils arrivent à l’adresse géographique. Ce nom d’emplacement peut inclure un numéro d’immeuble, un numéro d’étage, un indicateur d’aile, un numéro de chambre, etc. Évitez les surnoms connus des seuls employés, qui peuvent induire les agents des services d’urgence en erreur.

- Identificateur d’emplacement qui permet aux utilisateurs de voir facilement que leur client a choisi l’emplacement correct. Le Skype Entreprise client concatène et affiche automatiquement les champs Emplacement et Ville découverts dans  son en-tête. Une bonne pratique consiste à ajouter l’adresse de rue du bâtiment à chaque identificateur d’emplacement (par exemple, « 1er étage \<street number>»). Sans l’adresse postale, un identificateur d’emplacement générique tel que « 1er étage » peut s’appliquer à n’importe quel immeuble de la ville.

- Si l’emplacement est approximatif car il est déterminé par un point d’accès sans fil, vous pouvez ajouter le mot **[Proche]** (par exemple, « À proximité du 1er étage 1234 »).

### <a name="planning-elins"></a>Planification des numéros d’identification de l’emplacement en cas d’urgence (ELIN)

Après avoir déterminé comment diviser l’espace de votre bâtiment en emplacements, vous devez décider du nombre de numéros ELIN à affecter à chaque emplacement. Par exemple, dans un immeuble à plusieurs étages ou multilocatif, différentes zones ERL peuvent être affectées à différentes zones d’urgence. En général, chaque étage d’un immeuble est désigné comme un emplacement. Chaque emplacement se voit alors affecté un ou plusieurs numéros ELIN, qui sont utilisés comme numéros d’appel durant un appel d’urgence. Contactez votre opérateur RTC pour connaître les numéros de téléphone que vous pouvez utiliser pour les numéros ELIN. Le tableau suivant fournit des exemples d’emplacements pour une adresse postale spécifique.

**Exemples d’affectations d’emplacements et de numéros ELIN**

|**Zone de l’immeuble**|**Location**|**ELIN**|
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

En utilisant l’option Du service Informations sur l’emplacement secondaire pour vous connecter à une base de données tierce, vous pouvez grouper et gérer des emplacements à l’aide d’une plateforme hors connexion. Outre la possibilité d’associer des emplacements à des identificateurs réseau, cette approche vous offre l’avantage d’associer des emplacements à un utilisateur. Cela signifie que le service Informations d’emplacement peut renvoyer plusieurs adresses, provenant du service Informations d’emplacement secondaire, à un client Skype Entreprise client. L’utilisateur peut alors choisir l’emplacement le plus approprié.

Pour s’intégrer au service Informations d’emplacement, la base de données tierce doit suivre le schéma Skype Entreprise Server demande d’emplacement/réponse. Pour plus d’informations, [voir Service Web pour le protocole de prise en charge E911](/openspecs/office_protocols/ms-e911ws/ab5d7449-2c15-434b-bf65-fdf38b8ffabd). Pour plus d’informations sur le déploiement d’un service Secondary Location Information, voir [Configure a secondary Location Information service in Skype Entreprise Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in the Deployment documentation.

Pour plus d’informations sur le renseignement de la base de données d’emplacements, voir [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) dans la documentation de déploiement.

## <a name="maintaining-the-location-database"></a>Mise à jour de la base de données d’emplacements

Une fois que vous avez renseigné la base de données des emplacements, vous devez développer une stratégie pour la mettre à jour au fur et à mesure que la configuration réseau change. Les questions suivantes vous permettront de déterminer comment maintenir la base de données des emplacements.

 **Comment allez-vous mettre à jour la base de données d’emplacements ?**

L’ajout de points d’accès sans fil, le recâblage du bureau (qui implique des affectations de commutateur différentes) et l’extension des sous-réseaux font partie des nombreux scénarios qui requièrent la mise à jour de la base de données des emplacements. Mettrez-vous directement à jour chaque emplacement individuel ou effectuerez-vous une mise à jour en bloc de tous les emplacements en utilisant un fichier CSV ?

 **Allez-vous utiliser une application SNMP pour faire correspondre les adresses MAC Skype Entreprise client aux identificateurs de port et de commutateur ?**

Si vous utilisez une application SNMP, vous devez développer un processus manuel permettant de garder les informations de châssis de commutateur et de port cohérentes entre l’application SNMP et la base de données des emplacements. Si l’application SNMP renvoie une adresse IP de châssis ou un ID de port qui n’est pas inclus dans la base de données, le service Informations d’emplacement ne peut pas renvoyer un emplacement au client.