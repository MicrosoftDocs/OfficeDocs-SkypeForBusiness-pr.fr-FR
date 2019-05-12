---
title: Récupération d’urgence test dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Effectuer une récupération système pour une Skype pour Business server du pool tester votre processus de récupération d’urgence documentée
ms.openlocfilehash: 55398b95be1cf5cec2cafa3a91a36536df92200e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924814"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Récupération d’urgence test dans Skype pour Business Server

Effectuer une récupération système pour une Skype pour Business server du pool tester votre processus de récupération d’urgence documentée. Ce test simule une défaillance matérielle complète pour un seul serveur et vous aidera à garantir que les ressources, les plans et les données sont disponibles pour la récupération. Essayez d’alterner l’angle du test chaque mois afin que votre organisation teste chaque fois la défaillance d’un autre serveur ou d’un autre équipement. 

Notez que le calendrier des tests de récupération d'urgence de votre organisation varie. Il est très important que les tests de récupération d’urgence ne soient ni ignorés ni négligés. 

Exporter votre Skype pour la topologie, des stratégies et paramètres de configuration de Business Server vers un fichier. Ce fichier peut, entre autres, être utilisé pour restaurer ces informations dans le magasin central de gestion après une mise à niveau, une défaillance matérielle ou un autre problème ayant entraîné une perte de données.

Importer votre Skype pour la topologie du serveur d’entreprise, des stratégies et paramètres de configuration pour le magasin Central de gestion ou sur l’ordinateur local comme indiqué dans les commandes suivantes : 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

Pour sauvegarder des données de production :

- Processus pour vider la base de données pour un périphérique de vidage fichier ou la bande de sauvegarde sauvegarder les bases de données RTC et LCSLog à l’aide de SQL Server standard.
- Sauvegardez les données dans un fichier ou sur une bande à l’aide de l’application de sauvegarde tierce.
- Créez un export XML de la base de données RTC intégrale à l’aide de l’applet de commande Export-CsUserData.
- Utilisez la sauvegarde du système de fichiers ou d’une sauvegarde tierce pour sauvegarder les journaux de contenu et de conformité de réunion.
- Utilisez l’outil de ligne de commande Export-CsConfiguration pour sauvegarder Skype pour les paramètres du serveur d’entreprise.

La première étape de la procédure de basculement comporte un déplacement forcé des utilisateurs du pool de production vers le pool de récupération d’urgence. Il s’agit d’un déplacement forcé, car le pool de production n’est pas disponible pour accepter le déplacement des utilisateurs.

Le Skype Business Server processus de déplacement utilisateur est en fait une modification apportée à un attribut de l’objet de compte d’utilisateur en plus d’une mise à jour sur la base de données RTC SQL. Ces données peuvent être restaurées à partir de l’unité de vidage de sauvegarde d’origine de la production SQL Server en utilisant le processus de restauration SQL Server standard ou un tiers sauvegarde/restauration utilitaire.

Après la restauration de ces données, les utilisateurs peuvent effectivement se connectent au pool de la récupération d’urgence et fonctionner comme d’habitude. Pour permettre aux utilisateurs de se connecter au pool de récupération d’urgence, une modification d’enregistrement DNS seront requise.

Référencée par les clients à l’aide de la configuration automatique et les enregistrements DNS SRV de la production Skype pour le pool d’entreprise :

- SRV : _sip._tls. \<domain> /CNAME : SIP. \<domain>
- CNAME : SIP. \<domain> /cvc-pool-1. \<domain>

Pour faciliter le basculement, cet enregistrement CNAME doit être mis à jour de manière à référencer le nom de domaine complet (FQDN) DROCSPool :

- CNAME : SIP.<domain> / DROCSPool. \<domain>
- SIP. \<domain>
- Violation d’accès.\<domain>
- webconf. \<domain>
