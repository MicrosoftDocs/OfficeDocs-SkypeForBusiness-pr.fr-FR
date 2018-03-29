---
title: Rapport détaillé de conférence dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Résumé : En savoir plus sur le rapport de détails de conférence utilisé dans Skype pour Business Server 2015.'
ms.openlocfilehash: 4c55b2f339aa3d591f01d73d0f60d8fbc0bb483f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="conference-detail-report-in-skype-for-business-server-2015"></a>Rapport détaillé de conférence dans Skype Entreprise Server 2015
 
**Résumé :** Obtenir des informations sur le rapport de détails de conférence utilisé dans Skype pour Business Server 2015.
  
Le rapport détaillé de conférence donne des informations détaillées sur tous les utilisateurs qui ont participé à une conférence. Vous pouvez par exemple voir des informations, telles que la date et l’heure auxquelles un utilisateur s’est joint à la conférence, la date et l’heure auxquelles l’utilisateur a quitté la conférence et l’agent utilisateur du point de terminaison qui a permis à l’utilisateur de se connecter à la conférence. Vous pouvez également afficher des informations sur le rôle de l’utilisateur dans chaque conférence (par exemple présentateur ou participant). Ce qui est peut-être le plus important, vous pouvez voir rapidement quels utilisateurs ont réussi à rejoindre et suivre la conférence et quels utilisateurs n’ont pas réussi à rejoindre et suivre la conférence.
  
## <a name="accessing-the-conference-detail-report"></a>Accès au rapport détaillé de conférence

Le rapport détaillé de conférence est accessible à partir des rapports suivants :
  
- Le [Rapport de contrôle appeler Admission dans Skype pour Business Server 2015](call-admission-control-report.md) (en cliquant sur la mesure de détail d’une conférence)
    
- Le [Rapport de liste de défaillance dans Skype pour Business Server 2015](failure-list-report.md) (en cliquant sur la mesure de la conférence)
    
- Le [Rapport d’activité utilisateur dans Skype pour Business Server 2015](user-activity-report.md) (en cliquant sur la mesure de l’URI de la conférence)
    
À partir du rapport de détail de conférence, vous pouvez accéder le [Rapport de Diagnostic dans Skype pour 2015 de serveur d’entreprise](diagnostic-report.md) en cliquant sur la mesure de l’état de Diagnostic (détail).
  
## <a name="filters"></a>Filtres

Aucun. Vous ne pouvez pas filtrer sur le rapport détaillé de conférence.
  
## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans la section Informations de conférence du rapport détaillé de conférence.
  
**Mesures des informations de conférence**

|**Nom**|**Description**|
|:-----|:-----|
|**URI de la conférence** <br/> |URI affectée à la conférence. Par exemple :  <br/> SIP:kmyer@litwareinc.com;GRUU;opaque=App:conf:focus:ID:drg2y8v4  <br/> |
|**FQDN du pool** <br/> |Nom de domaine complet du pool de serveurs d’inscriptions ou serveur Edge impliqué dans une session.  <br/> |
|**Heure de début** <br/> |Date et heure auxquelles la conférence a commencé.  <br/> |
|**Organisateur** <br/> |Adresse SIP de l’utilisateur qui a organisé la conférence.  <br/> |
|**Heure de fin** <br/> |Date et heure de fin de la conférence.  <br/> |
   
Le tableau qui suit répertorie les informations fournies dans la section Participation à la conférence du rapport détaille de conférence.
  
**Mesures de Participation de conférence**

|**Nom**|**Description**|
|:-----|:-----|
|**Utilisateur** <br/> |Adresse SIP de l’utilisateur qui a participé à la conférence.  <br/> |
|**Rôle** <br/> |Rôle (par exemple, présentateur) joué par le participant à la conférence.  <br/> |
|**Connectivité** <br/> |Connectivité réseau (généralement Depuis interne ou Depuis externe) du participant.  <br/> |
|**Heure d’arrivée** <br/> |Date et heure auxquelles le participant a rejoint la conférence.  <br/> |
|**Heure de départ** <br/> |Date et heure auxquelles le participant a quitté la conférence.  <br/> |
|**Agent utilisateur** <br/> |Identificateur du logiciel utilisé par le point de terminaison du participant.  <br/> |
|**Rapports de diagnostic** <br/> |Fournit des informations de diagnostic et de résolution des problèmes, notamment les codes de réponse SIP, les en-têtes de diagnostic, les temps de connexion à la conférence et les ID de diagnostic des sessions qui ont échoué.  <br/> |
   
Le tableau suivant répertorie les informations fournies dans la section modalités de la conférence de l’état de détail de conférence.
  
**Mesures de modalités de conférence**

|**Nom**|**Description**|
|:-----|:-----|
|**Utilisateur** <br/> |Adresse SIP de l’utilisateur qui a participé à la conférence.  <br/> |
|**Heure d’arrivée** <br/> |Date et heure auxquelles le participant a rejoint la conférence.  <br/> |
|**Heure de départ** <br/> |Date et heure auxquelles un participant a quitté la conférence.  <br/> |
|**URI du serveur de conférence** <br/> |URI du serveur de conférence utilisé dans la conférence.  <br/> |
|**Rapports de diagnostic** <br/> |Fournit des informations de diagnostic et de résolution des problèmes, notamment les codes de réponse SIP, les en-têtes de diagnostic, les temps de connexion à la conférence et les ID de diagnostic des sessions qui ont échoué.  <br/> |
   

