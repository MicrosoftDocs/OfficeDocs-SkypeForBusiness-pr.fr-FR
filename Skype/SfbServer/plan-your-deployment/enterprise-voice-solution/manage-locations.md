---
title: Gestion des emplacements pour les fournisseurs de service SIP Trunk dans Skype entreprise Server
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
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: Les décisions nécessaires pour la planification d’une base de données d’informations d’emplacement ou d’une base de données externe similaire pour un déploiement E9-1-1 à l’aide de fournisseurs de trunking SIP dans Skype entreprise Server Voice.
ms.openlocfilehash: 81ec257b30d2916bb4df2a4590b9abfc1b270375
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802724"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>Gestion des emplacements pour les fournisseurs de service SIP Trunk dans Skype entreprise Server

Les décisions nécessaires pour la planification d’une base de données d’informations d’emplacement ou d’une base de données externe similaire pour un déploiement E9-1-1 à l’aide de fournisseurs de trunking SIP dans Skype entreprise Server Voice.

Pour configurer Skype entreprise Server de façon à ce qu’il détecte automatiquement les clients au sein d’un réseau, vous devez remplir la base de données de service des informations d’emplacement auprès d’un réseau de Wiremap et publier les emplacements, ou créer un lien vers une base de données externe contenant déjà mappages appropriés. Dans le cadre de ce processus, vous devez valider les adresses géographiques des emplacements avec votre fournisseur de services E9-1-1. Pour plus d’informations, reportez-vous à [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) dans la documentation de déploiement.

Renseignez la base de données du service Informations d’emplacement avec un emplacement d’intervention d’urgence (ERL), composé d’une adresse géographique et de l’adresse spécifique au sein d’un bâtiment. Le champ d' **emplacement** du service des informations d’emplacement, qui correspond à un emplacement spécifique au sein d’un immeuble, a une longueur maximale de 20 caractères (espaces compris). En respectant cette limite, essayez d’inclure les éléments suivants :

- Nom facile à comprendre qui identifie l’emplacement de l’appelant 911 pour s’assurer que les agents des services d’urgence trouvent l’emplacement spécifique rapidement lorsqu’ils arrivent à l’adresse géographique. Ce nom d’emplacement peut inclure un numéro d’immeuble, un numéro d’étage, un indicateur d’aile, un numéro de chambre, etc. Évitez les surnoms connus des seuls employés, qui peuvent induire les agents des services d’urgence en erreur.

- Un identificateur d’emplacement qui permet aux utilisateurs de voir facilement que leur client Skype entreprise a choisi le bon emplacement. Le client Skype entreprise concatène automatiquement et affiche les champs **emplacement** et **ville** détectés dans son en-tête. Il est recommandé d’ajouter l’adresse postale du bâtiment à chaque identificateur d’emplacement (par exemple, « 1er étage <street number>»). Sans l’adresse postale, un identificateur d’emplacement générique tel que « 1er étage » peut s’appliquer à n’importe quel immeuble de la ville.

- Si l’emplacement est approximativement déterminé par un point d’accès sans fil, vous pouvez ajouter le mot **[proche]** (par exemple, « 1er étage 1234 »).

> [!NOTE]
> Les emplacements ajoutés à la base de données d’emplacement central ne sont pas disponibles pour le client tant qu’ils n’ont pas été publiés à l’aide d’une commande Skype entreprise Server Management Shell et répliqués dans les boutiques locales du pool. Pour plus d’informations, reportez-vous à [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) dans la documentation de déploiement.

Les sections suivantes abordent les points à prendre en considération lorsque vous remplissez et mettez à jour la base de données des emplacements.

## <a name="populating-the-location-database"></a>Remplissage de la base de données d’emplacements

Les questions suivantes vous permettront de déterminer comment remplir la base de données des emplacements.

 **Quel processus allez-vous adopter pour remplir la base de données d’emplacements ?**

Où sont stockées les données et quelles étapes devez-vous suivre pour les convertir au format requis par la base de données d’emplacements ? Allez-vous ajouter des emplacements individuellement ou en bloc en utilisant un fichier CSV ?

 **Disposez-vous d’une base de données tierce qui contient déjà un mappage des emplacements ?**

À l’aide de l’option de service des informations de lieu secondaire pour vous connecter à une base de données tierce, vous pouvez regrouper et gérer les emplacements à l’aide d’une plateforme hors connexion. Outre la possibilité d’associer des emplacements à des identificateurs réseau, cette approche vous offre l’avantage d’associer des emplacements à un utilisateur. Cela signifie que le service d’information d’emplacement peut retourner plusieurs adresses à partir du service d’information d’emplacement secondaire, vers un client Skype entreprise. L’utilisateur peut alors choisir l’emplacement le plus approprié.

Pour être intégré au service d’information d’emplacement, la base de données tierce doit suivre le schéma de requête/réponse d’emplacement du serveur Lync. Pour plus d’informations, consultez [« [MS-E911WS] : service Web pour E911 support Protocol Specification »](https://go.microsoft.com/fwlink/p/?linkid=213819). Pour plus d’informations sur le déploiement d’un service d’information d’emplacement secondaire, voir [configurer un service d’information d’emplacement secondaire dans Skype entreprise Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) dans la documentation de déploiement.

Pour plus d’informations sur le renseignement de la base de données d’emplacements, reportez-vous à [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) dans la documentation de déploiement.

## <a name="maintaining-the-location-database"></a>Mise à jour de la base de données d’emplacements

Une fois que vous avez renseigné la base de données des emplacements, vous devez développer une stratégie pour la mettre à jour au fur et à mesure que la configuration réseau change. Les questions suivantes vous permettront de déterminer comment maintenir la base de données des emplacements.

 **Comment allez-vous mettre à jour la base de données d’emplacements ?**

L’ajout de points d’accès sans fil, le recâblage du bureau (qui implique des affectations de commutateur différentes) et l’extension des sous-réseaux font partie des nombreux scénarios qui requièrent la mise à jour de la base de données des emplacements. Mettrez-vous directement à jour chaque emplacement individuel ou effectuerez-vous une mise à jour en bloc de tous les emplacements en utilisant un fichier CSV ?

 **Ferez-vous appel à une application SNMP pour associer des adresses MAC de client Lync aux identificateurs de port et de commutateur ?**

Si vous utilisez une application SNMP, vous devez développer un processus manuel permettant de garder les informations de châssis de commutateur et de port cohérentes entre l’application SNMP et la base de données des emplacements. Si l’application SNMP renvoie une adresse IP du châssis ou un ID de port qui n’est pas inclus dans la base de données, le service d’information d’emplacement n’est pas en mesure de renvoyer un emplacement au client.


