---
title: Gérer les emplacements pour les fournisseurs de services de trunk SIP dans Skype Entreprise Server
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
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: Décisions nécessaires à la planification d’une base de données d’informations d’emplacement ou d’une base de données externe similaire pour un déploiement E9-1-1 à l’aide de fournisseurs de trunking SIP, Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 4667ea571fe3bbb022c8dd1ee1483e6195165ec9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855291"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>Gérer les emplacements pour les fournisseurs de services de trunk SIP dans Skype Entreprise Server

Décisions nécessaires à la planification d’une base de données d’informations d’emplacement ou d’une base de données externe similaire pour un déploiement E9-1-1 à l’aide de fournisseurs de trunking SIP, Skype Entreprise Server Voix Entreprise.

Pour configurer Skype Entreprise Server afin de localiser automatiquement des clients au sein d’un réseau, vous devez remplir la base de données du service Informations d’emplacement avec un schéma de câblage réseau et publier les emplacements, ou établir un lien vers une base de données externe qui contient déjà les mappages corrects. Dans le cadre de ce processus, vous devez valider les adresses géographiques des emplacements avec votre fournisseur de services E9-1-1. Pour plus d’informations, voir [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) dans la documentation de déploiement.

Vous renseignez la base de données du service Informations d’emplacement avec un emplacement d’intervention d’urgence (ERL), composé d’une adresse géographique et de l’adresse spécifique au sein d’un bâtiment. Le champ Emplacement **du** service Informations sur l’emplacement, qui est l’emplacement spécifique dans un bâtiment, a une longueur maximale de 20 caractères (espaces compris). En respectant cette limite, essayez d’inclure les éléments suivants :

- Nom facile à comprendre qui identifie l’emplacement de l’appelant 911 pour s’assurer que les agents des services d’urgence trouvent l’emplacement spécifique rapidement lorsqu’ils arrivent à l’adresse géographique. Ce nom d’emplacement peut inclure un numéro d’immeuble, un numéro d’étage, un indicateur d’aile, un numéro de chambre, etc. Évitez les surnoms connus des seuls employés, qui peuvent induire les agents des services d’urgence en erreur.

- Identificateur d’emplacement qui permet aux utilisateurs de voir facilement que Skype Entreprise client a choisi l’emplacement correct. Le Skype Entreprise client concatène et affiche automatiquement les  champs  Emplacement et Ville découverts dans son en-tête. Une bonne pratique consiste à ajouter l’adresse de rue du bâtiment à chaque identificateur d’emplacement (par exemple, « 1er étage \<street number> »). Sans l’adresse postale, un identificateur d’emplacement générique tel que « 1er étage » peut s’appliquer à n’importe quel immeuble de la ville.

- Si l’emplacement est approximatif car il est déterminé par un point d’accès sans fil, vous pouvez ajouter le mot **[Proche]** (par exemple, « À proximité du 1er étage 1234 »).

> [!NOTE]
> Les emplacements ajoutés à la base de données centrale des emplacements ne sont pas disponibles pour le client tant qu’ils ne sont pas publiés à l’aide d’une commande Skype Entreprise Server Management Shell et répliqués dans les magasins locaux du pool. Pour plus d’informations, voir [Publishing the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-location-database) dans la documentation de déploiement.

Les sections suivantes abordent les points à prendre en considération lorsque vous remplissez et mettez à jour la base de données des emplacements.

## <a name="populating-the-location-database"></a>Remplissage de la base de données d’emplacements

Les questions suivantes vous permettront de déterminer comment remplir la base de données des emplacements.

 **Quel processus allez-vous adopter pour remplir la base de données d’emplacements ?**

Où sont stockées les données et quelles étapes devez-vous suivre pour les convertir au format requis par la base de données d’emplacements ? Allez-vous ajouter des emplacements individuellement ou en bloc en utilisant un fichier CSV ?

 **Disposez-vous d’une base de données tierce qui contient déjà un mappage des emplacements ?**

En utilisant l’option Du service Informations sur l’emplacement secondaire pour vous connecter à une base de données tierce, vous pouvez grouper et gérer des emplacements à l’aide d’une plateforme hors connexion. Outre la possibilité d’associer des emplacements à des identificateurs réseau, cette approche vous offre l’avantage d’associer des emplacements à un utilisateur. Cela signifie que le service Informations d’emplacement peut renvoyer plusieurs adresses, provenant du service Informations d’emplacement secondaire, à un client Skype Entreprise client. L’utilisateur peut alors choisir l’emplacement le plus approprié.

Pour s’intégrer au service Informations d’emplacement, la base de données tierce doit suivre le schéma de demande/réponse d’emplacement Lync Server. Pour plus d’informations, voir  [« [MS-E911WS]: Web Service for E911 Support Protocol Specification](/openspecs/office_protocols/ms-e911ws/ab5d7449-2c15-434b-bf65-fdf38b8ffabd)». Pour plus d’informations sur le déploiement d’un service Secondary Location Information, voir [Configure a secondary Location Information service in Skype Entreprise Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in the Deployment documentation.

Pour plus d’informations sur le renseignement de la base de données d’emplacements, voir [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) dans la documentation de déploiement.

## <a name="maintaining-the-location-database"></a>Mise à jour de la base de données d’emplacements

Une fois que vous avez renseigné la base de données des emplacements, vous devez développer une stratégie pour la mettre à jour au fur et à mesure que la configuration réseau change. Les questions suivantes vous permettront de déterminer comment maintenir la base de données des emplacements.

 **Comment allez-vous mettre à jour la base de données d’emplacements ?**

L’ajout de points d’accès sans fil, le recâblage du bureau (qui implique des affectations de commutateur différentes) et l’extension des sous-réseaux font partie des nombreux scénarios qui requièrent la mise à jour de la base de données des emplacements. Mettrez-vous directement à jour chaque emplacement individuel ou effectuerez-vous une mise à jour en bloc de tous les emplacements en utilisant un fichier CSV ?

 **Ferez-vous appel à une application SNMP pour associer des adresses MAC de client Lync aux identificateurs de port et de commutateur ?**

Si vous utilisez une application SNMP, vous devez développer un processus manuel permettant de garder les informations de châssis de commutateur et de port cohérentes entre l’application SNMP et la base de données des emplacements. Si l’application SNMP renvoie une adresse IP de châssis ou un ID de port qui n’est pas inclus dans la base de données, le service Informations d’emplacement ne peut pas renvoyer un emplacement au client.