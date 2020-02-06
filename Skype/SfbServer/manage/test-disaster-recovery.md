---
title: Test de reprise après sinistre dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Effectuer une récupération du système pour un serveur de pool de serveurs Skype entreprise pour tester votre processus de récupération d’urgence documenté
ms.openlocfilehash: f3eba25d59c56f085b9bd6d347fcde910f11a00d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817300"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Test de reprise après sinistre dans Skype entreprise Server

Effectuez une récupération du système pour un serveur de pool de serveurs Skype entreprise pour tester votre processus de récupération d’urgence documenté. Ce test simule une panne matérielle complète pour un serveur et permet de garantir la disponibilité des ressources, plans et données pour la récupération. Essayez d’alterner l’angle du test chaque mois afin que votre organisation teste chaque fois la défaillance d’un autre serveur ou d’un autre équipement. 

Notez que le calendrier des tests de récupération d'urgence de votre organisation varie. Il est très important que les tests de récupération d’urgence ne soient ni ignorés ni négligés. 

Exportez votre topologie, vos stratégies et vos paramètres de configuration de Skype entreprise Server vers un fichier. Ce fichier peut, entre autres, être utilisé pour restaurer ces informations dans le magasin central de gestion après une mise à niveau, une défaillance matérielle ou un autre problème ayant entraîné une perte de données.

Importez vos paramètres de topologie, de stratégies et de configuration de Skype entreprise Server sur le magasin de gestion central ou sur l’ordinateur local, comme illustré dans les commandes suivantes : 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

Pour sauvegarder les données de production :

- Sauvegardez les bases de données RTC et LCSLog à l’aide du processus de sauvegarde SQL Server standard pour vider la base de données sur un fichier ou un appareil de vidage de bande.
- Sauvegardez les données dans un fichier ou sur une bande à l’aide de l’application de sauvegarde tierce.
- Créez un export XML de la base de données RTC intégrale à l’aide de l’applet de commande Export-CsUserData.
- Utilisez la sauvegarde du système de fichiers ou la sauvegarde tierce pour sauvegarder les journaux du contenu et de la conformité de la réunion.
- Utilisez l’outil de ligne de commande Export-CsConfiguration pour sauvegarder les paramètres de Skype entreprise Server.

La première étape de la procédure de basculement comporte un déplacement forcé des utilisateurs du pool de production vers le pool de récupération d’urgence. Il s’agit d’un déplacement forcé, car le pool de production n’est pas disponible pour accepter le déplacement des utilisateurs.

Le processus de déplacement d’un utilisateur de Skype entreprise Server est une modification apportée à un attribut sur l’objet compte d’utilisateur, en plus de la mise à jour d’un enregistrement dans la base de données SQL RTC. Ces données peuvent être restaurées à partir de l’appareil de vidage de sauvegarde d’origine à partir du serveur SQL Server en utilisant le processus de restauration standard de SQL Server, ou à l’aide d’une utilitaire de sauvegarde/restauration tierce.

Une fois ces données restaurées, les utilisateurs peuvent se connecter au pool de reprise après sinistre et s’exécuter normalement. Pour permettre aux utilisateurs de se connecter au pool de récupération d’urgence, une modification de l’enregistrement DNS sera requise.

Le pool Skype entreprise de production sera référencé par des clients à l’aide de la configuration automatique et des enregistrements SRV DNS de :

- SRV : _sip. _tls. \<Domain>/CNAME : SIP. \<> de domaine
- CNAME : SIP. \<Domain>/CVC-pool-1. \<> de domaine

Pour faciliter le basculement, cet enregistrement CNAME doit être mis à jour de manière à référencer le nom de domaine complet (FQDN) DROCSPool :

- CNAME : SIP.<domain> /DROCSPool. \<> de domaine
- SIP. \<> de domaine
- > AV\<. Domain
- webconf. \<> de domaine
