---
title: Gestion des emplacements pour les passerelles ELIN dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: Décisions nécessaires à la planification d’une base de données d’informations d’emplacement ou d’une base de données externe similaire pour un déploiement E9-1-1 à l’aide de passerelles ELIN dans Skype entreprise Server Voice.
ms.openlocfilehash: e1645be8ed1c6188d1976d794727d0668b79c12e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276928"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a>Gestion des emplacements pour les passerelles ELIN dans Skype entreprise Server

Décisions nécessaires à la planification d’une base de données d’informations d’emplacement ou d’une base de données externe similaire pour un déploiement E9-1-1 à l’aide de passerelles ELIN dans Skype entreprise Server Voice.

Pour que Skype entreprise Server fournisse automatiquement des emplacements pour les clients au sein d’un réseau, vous devez effectuer les tâches suivantes:

- Remplissez la base de données de service informations d’emplacement auprès d’un réseau de Wiremap, puis incluez les numéros d’identification d’emplacement d’urgence (ELINs) dans le champ CompanyName.

- Publiez les emplacements afin qu’ils soient disponibles pour les clients dans votre réseau.

- Téléchargez les numéros d’identification de l’emplacement en cas d’urgence vers la base de données ALI (Automatic Location Identification) de votre opérateur PSTN.

Pour plus d’informations sur l’exécution de ces tâches, reportez-vous à [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) dans la documentation de déploiement.

> [!NOTE]
> Les emplacements ajoutés à la base de données d’emplacement central ne sont pas disponibles pour le client tant qu’ils n’ont pas été publiés à l’aide d’une commande Skype entreprise Server Management Shell et répliqués dans les boutiques locales du pool. Pour plus d’informations, reportez-vous à [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) dans la documentation de déploiement.

Cette section décrit les éléments à prendre en compte lorsque vous prévoyez de mettre à jour ou maintenir la base de données des emplacements.

## <a name="planning-emergency-locations"></a>Planification des emplacements d’urgence

Lorsque vous utilisez des passerelles ELIN, vous remplissez la base de données de service des informations d’emplacement à l’aide de l’adresse postale, d’un emplacement spécifique au sein d’un bâtiment et au moins un ELIN pour chaque emplacement. Durant la phase de planification, il est recommandé de décider du nom des emplacements et de l’affectation des numéros d’identification de l’emplacement en cas d’urgence.

### <a name="planning-location-names"></a>Planification des noms d’emplacement

Le champ d' **emplacement** du service des informations d’emplacement, qui contient l’emplacement spécifique au sein d’un immeuble, a une longueur maximale de 20 caractères (espaces compris). En respectant cette limite, essayez d’inclure les éléments suivants :

- Nom facile à comprendre qui identifie l’emplacement de l’appelant 911 pour s’assurer que les agents des services d’urgence trouvent l’emplacement spécifique rapidement lorsqu’ils arrivent à l’adresse géographique. Ce nom d’emplacement peut inclure un numéro d’immeuble, un numéro d’étage, un indicateur d’aile, un numéro de chambre, etc. Évitez les surnoms connus des seuls employés, qui peuvent induire les agents des services d’urgence en erreur.

- Identificateur d’emplacement qui aide les utilisateurs à vérifier que leur client a sélectionné l’emplacement correct. Le client Skype entreprise concatène automatiquement et affiche les champs **emplacement** et **ville** détectés dans son en-tête. Il est recommandé d’ajouter l’adresse postale du bâtiment à chaque identificateur d’emplacement (par exemple, «1er étage <street number>»). Sans l’adresse postale, un identificateur d’emplacement générique tel que « 1er étage » peut s’appliquer à n’importe quel immeuble de la ville.

- Si l’emplacement est approximativement déterminé par un point d’accès sans fil, il est possible que vous souhaitiez ajouter le mot **[proche]** (par exemple, «bientôt 1er étage 1234»).

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

À l’aide de l’option de service des informations de lieu secondaire pour vous connecter à une base de données tierce, vous pouvez regrouper et gérer les emplacements à l’aide d’une plateforme hors connexion. Outre la possibilité d’associer des emplacements à des identificateurs réseau, cette approche vous offre l’avantage d’associer des emplacements à un utilisateur. Cela signifie que le service d’information d’emplacement peut retourner plusieurs adresses à partir du service d’information d’emplacement secondaire, vers un client Skype entreprise. L’utilisateur peut alors choisir l’emplacement le plus approprié.

Pour être intégré au service d’information d’emplacement, la base de données tierce doit suivre le schéma de demande/réponse d’emplacement du serveur Skype entreprise Server. Pour plus d’informations, consultez [service Web pour le protocole de support E911](https://go.microsoft.com/fwlink/p/?linkid=213819). Pour plus d’informations sur le déploiement d’un service d’information d’emplacement secondaire, voir [configurer un service d’information d’emplacement secondaire dans Skype entreprise Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) dans la documentation de déploiement.

Pour plus d’informations sur le renseignement de la base de données d’emplacements, reportez-vous à [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) dans la documentation de déploiement.

## <a name="maintaining-the-location-database"></a>Mise à jour de la base de données d’emplacements

Une fois que vous avez renseigné la base de données des emplacements, vous devez développer une stratégie pour la mettre à jour au fur et à mesure que la configuration réseau change. Les questions suivantes vous permettront de déterminer comment maintenir la base de données des emplacements.

 **Comment allez-vous mettre à jour la base de données d’emplacements ?**

L’ajout de points d’accès sans fil, le recâblage du bureau (qui implique des affectations de commutateur différentes) et l’extension des sous-réseaux font partie des nombreux scénarios qui requièrent la mise à jour de la base de données des emplacements. Mettrez-vous directement à jour chaque emplacement individuel ou effectuerez-vous une mise à jour en bloc de tous les emplacements en utilisant un fichier CSV ?

 **Allez-vous utiliser une application SNMP pour faire correspondre les adresses MAC client Skype entreprise et les identificateurs de ports et de switches?**

Si vous utilisez une application SNMP, vous devez développer un processus manuel permettant de garder les informations de châssis de commutateur et de port cohérentes entre l’application SNMP et la base de données des emplacements. Si l’application SNMP renvoie une adresse IP du châssis ou un ID de port qui n’est pas inclus dans la base de données, le service d’information d’emplacement n’est pas en mesure de renvoyer un emplacement au client.


