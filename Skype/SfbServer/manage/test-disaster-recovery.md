---
title: Test de récupération d’urgence dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Effectuer une récupération système pour un serveur Skype Entreprise Server pool de serveurs pour tester votre processus de récupération d’urgence documenté
ms.openlocfilehash: 2d6fa097061b470814887f1e13eaf4748de6e4f3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863501"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Test de récupération d’urgence dans Skype Entreprise Server

Effectuez une récupération système pour un serveur Skype Entreprise Server pool de serveurs pour tester votre processus de récupération d’urgence documenté. Ce test simule une défaillance matérielle complète pour un serveur et garantit que les ressources, les plans et les données sont disponibles pour la récupération. Essayez de faire pivoter le focus du test chaque mois afin que votre organisation teste chaque fois la défaillance d’un autre serveur ou d’un autre équipement. 

Notez que la planification selon laquelle les organisations effectuent des tests de récupération d’urgence varie. Il est très important que les tests de récupération d’urgence ne sont pas ignorés ou ignorés. 

Exportez Skype Entreprise Server topologie, stratégies et paramètres de configuration dans un fichier. Ce fichier peut, entre autres, être utilisé pour restaurer ces informations dans le magasin central de gestion après une mise à niveau, une défaillance matérielle ou un autre problème qui a entraîné une perte de données.

Importez Skype Entreprise Server topologie, stratégies et paramètres de configuration dans le magasin central de gestion ou sur l’ordinateur local, comme indiqué dans les commandes suivantes : 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

Pour la protection des données de production :

- Sauvegardez les bases de données RTC et LCSLog à l’aide du processus de sauvegarde SQL Server standard pour vider la base de données sur un périphérique de vidage de fichier ou de bande.
- Utilisez une application de sauvegarde tierce pour sauvegarder les données dans un fichier ou sur bande.
- Utilisez la cmdlet Export-CsUserData pour créer une exportation XML de toute la base de données RTC.
- Utilisez la sauvegarde du système de fichiers ou la sauvegarde tierce pour sauvegarder le contenu des réunions et les journaux de conformité.
- Utilisez lExport-CsConfiguration de ligne de commande pour Skype Entreprise Server paramètres.

La première étape de la procédure de récupération d’urgence comprend un déplacement forcé d’utilisateurs du pool de production vers le pool de récupération d’urgence. Il s’agit d’un déplacement forcé, car le pool de production ne sera pas disponible pour accepter le déplacement de l’utilisateur.

Le Skype Entreprise Server de déplacement d’utilisateurs est en fait une modification d’un attribut sur l’objet de compte d’utilisateur en plus d’une mise à jour d’enregistrement sur la base de données SQL RTC. Ces données peuvent être restaurées à partir du périphérique de vidage de sauvegarde d’origine à partir du SQL Server de production à l’aide du processus de restauration SQL Server standard ou à l’aide d’un utilitaire de sauvegarde/restauration tiers.

Une fois ces données restaurées, les utilisateurs peuvent effectivement se connecter au pool de récupération d’urgence et fonctionner comme d’habitude. Pour permettre aux utilisateurs de se connecter au pool de récupération d’urgence, une modification d’enregistrement DNS est requise.

Le pool de Skype Entreprise production sera référencé par les clients à l’aide de la configuration automatique et des enregistrements SRV DNS des :

- SRV : _sip._tls.\<domain> /CNAME : SIP.\<domain>
- CNAME : SIP.\<domain> /cvc-pool-1.\<domain>

Pour faciliter le perf, cet enregistrement CNAME doit être mis à jour pour référencer le FQDN DROCSPool :

- CNAME : SIP.\<domain> /DROCSPool.\<domain>
- Sip.\<domain>
- Av.\<domain>
- webconf.\<domain>
