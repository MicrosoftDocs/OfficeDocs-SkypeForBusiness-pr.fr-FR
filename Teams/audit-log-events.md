---
title: "Rechercher des événements Microsoft Teams dans le journal d'audit | Support Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: tutorial
ms.service: msteams
description: "Découvrez comment récupérer des données Microsoft Teams à partir du journal d'audit."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: ac68a0c2f795d20a8f6932e06a8ce4cab290e23c
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/20/2017
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Rechercher des événements Microsoft Teams dans le journal d'audit
==================================================

Le journal d'audit fournit des fonctionnalités de recherche ad hoc d'événements importants survenus dans les services Office 365. Dans le cas particulier Microsoft Teams, voici quelques exemples d'événements capturés :

-   Création d'une équipe

-   Suppression d'une équipe

-   Ajout d'un canal

-   Modification d'un paramètre

La liste complète des événements Office 365 est relativement étendue et disponible [ici](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities).

Avant de pouvoir examiner les activités d'audit, la fonctionnalité d'audit doit d'abord être activée. Pour activer la fonctionnalité d'audit, accédez au Centre d'administration *Sécurité et Conformité*. Sous *Rechercher une activité*, cliquez sur **Démarrer l'enregistrement**. Après 24 heures, les données d'audit seront disponibles via *Recherche du journal d'audit* située sous l'onglet *Recherche et examen*.


| |  |
|---------|---------|
|![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image1.png)<br></br>Important     |Les données d'audit sont uniquement disponibles à partir du point d'activation de la fonctionnalité d'audit.         |

![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image2.png)

À présent, passons à la récupération des données Microsoft Teams à partir du journal d'audit :

1.  Pour récupérer des informations du journal d'audit, accédez au Centre d'administration [Sécurité et Conformité](https://go.microsoft.com/fwlink/?linkid=855775). Sous *Recherche et examen*, sélectionnez **Recherche du journal d'audit.**

    a.  Microsoft Teams a défini des activités d'audit qui peuvent être sélectionnées comme indiqué ci-après.

![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  Une fois les activités qui vous intéressent sélectionnées, fournissez une plage de dates et des utilisateurs pour lesquels vous souhaitez récupérer les informations Microsoft Teams. Cliquez sur **Rechercher** pour récupérer les résultats.

3.  Vous pouvez exporter ces informations au format Excel et les filtrer en fonction de vos besoins.


|  | |
|---------|---------|
|![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image1.png)<br></br>Important |Si la fonction d'audit n'a pas été préalablement activée, vous devez l'activer pour obtenir des données dans le journal d'audit.         |
