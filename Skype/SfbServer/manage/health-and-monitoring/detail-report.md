---
title: Rapport détaillé de conférence dans Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Résumé : Découvrez le rapport détaillé de conférence utilisés dans Skype pour Business Server.'
ms.openlocfilehash: 025e8bda6e26baf261aeb3729907a3f13c220774
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27214594"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a>Rapport détaillé de conférence dans Skype pour Business Server

**Résumé :** Découvrez le rapport détaillé de conférence utilisés dans Skype pour Business Server.

Le rapport détaillé de conférence donne des informations détaillées sur tous les utilisateurs qui ont participé à une conférence. Vous pouvez par exemple voir des informations, telles que la date et l’heure auxquelles un utilisateur s’est joint à la conférence, la date et l’heure auxquelles l’utilisateur a quitté la conférence et l’agent utilisateur du point de terminaison qui a permis à l’utilisateur de se connecter à la conférence. Vous pouvez également afficher des informations sur le rôle de l’utilisateur dans chaque conférence (par exemple présentateur ou participant). Ce qui est peut-être le plus important, vous pouvez voir rapidement quels utilisateurs ont réussi à rejoindre et suivre la conférence et quels utilisateurs n’ont pas réussi à rejoindre et suivre la conférence.

## <a name="accessing-the-conference-detail-report"></a>Accès au rapport détaillé de conférence

Le rapport détaillé de conférence est accessible à partir des rapports suivants :

- Le [Call Admission Control Report](call-admission-control-report.md) (en cliquant sur la mesure Détails d’une conférence)

- Le [Failure List Report](failure-list-report.md) (en cliquant sur la mesure Conférence)

- Le [User Activity Report](call-diagnostic-reports-per-user.md) (en cliquant sur la mesure URI de la conférence)

Dans le rapport détaillé de conférence, vous pouvez accéder le [Diagnostic signalé](diagnostic-report.md) en cliquant sur la mesure rapport de Diagnostic (détail).

## <a name="filters"></a>Filtres

Aucun. Vous ne pouvez pas filtrer sur le rapport détaillé de conférence.

## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans la section Informations de conférence du rapport détaillé de conférence.

**Mesures des informations de conférence**


| **Nom**                 | **Description**                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| **URI de la conférence** <br/> | URI affectée à la conférence. Par exemple :  <br/> sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4  <br/> |
| **FQDN du pool** <br/>      | Nom de domaine complet du pool de serveurs d’inscriptions ou serveur Edge impliqué dans une session.  <br/>                             |
| **Heure de début** <br/>     | Date et heure auxquelles la conférence a commencé.  <br/>                                                                          |
| **Organisateur** <br/>      | Adresse SIP de l’utilisateur qui a organisé la conférence.  <br/>                                                               |
| **Heure de fin** <br/>       | Date et heure de fin de la conférence.  <br/>                                                                            |

Le tableau qui suit répertorie les informations fournies dans la section Participation à la conférence du rapport détaille de conférence.

**Mesures de participation à la conférence**

|**Nom**|**Description**|
|:-----|:-----|
|**Utilisateur** <br/> |Adresse SIP de l’utilisateur qui a participé à la conférence.  <br/> |
|**Rôle** <br/> |Rôle (par exemple, présentateur) joué par le participant à la conférence.  <br/> |
|**Connectivité** <br/> |Connectivité réseau (généralement Depuis interne ou Depuis externe) du participant.  <br/> |
|**Heure d’arrivée** <br/> |Date et heure auxquelles le participant a rejoint la conférence.  <br/> |
|**Heure de départ** <br/> |Date et heure auxquelles le participant a quitté la conférence.  <br/> |
|**Agent utilisateur** <br/> |Identifiant du logiciel utilisé par le point de terminaison du participant.  <br/> |
|**Rapports de diagnostic** <br/> |Fournit des informations de diagnostic et de résolution des problèmes, notamment les codes de réponse SIP, les en-têtes de diagnostic, les temps de connexion à la conférence et les ID de diagnostic des sessions qui ont échoué.  <br/> |

Le tableau suivant répertorie les informations fournies dans la section modalités de conférence du rapport détaillé de conférence.

**Mesures des modalités de conférence**

|**Nom**|**Description**|
|:-----|:-----|
|**Utilisateur** <br/> |Adresse SIP de l’utilisateur qui a participé à la conférence.  <br/> |
|**Heure d’arrivée** <br/> |Date et heure auxquelles le participant a rejoint la conférence.  <br/> |
|**Heure de départ** <br/> |Date et heure auxquelles un participant a quitté la conférence.  <br/> |
|**URI du serveur de conférence** <br/> |URI du serveur de conférence utilisé dans la conférence.  <br/> |
|**Rapports de diagnostic** <br/> |Fournit des informations de diagnostic et de résolution des problèmes, notamment les codes de réponse SIP, les en-têtes de diagnostic, les temps de connexion à la conférence et les ID de diagnostic des sessions qui ont échoué.  <br/> |


