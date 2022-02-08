---
title: Rapport de contrôle d’admission des appels Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
description: 'Résumé : Découvrez les rapports de contrôle d’admission des appels utilisés dans Skype Entreprise Server.'
ms.openlocfilehash: d0b32f399b01c18252dbd5593468e86e1ba7283c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384282"
---
# <a name="call-admission-control-report-in-skype-for-business-server"></a>Rapport de contrôle d’admission des appels Skype Entreprise Server
 
**Résumé :** Découvrez les rapports de contrôle d’admission des appels utilisés dans Skype Entreprise Server.
  
Le rapport de contrôle d’admission des appels fournit des informations sur les sessions d’égal à égal et de conférence qui ont été menées dans le cadre de restrictions définies par le contrôle d’admission des appels. Le contrôle d’admission des appels permet aux administrateurs d’autoriser (ou de ne pas autoriser) les sessions de communication en fonction des contraintes de bande passante. Par exemple, les administrateurs peuvent créer des stratégies qui imposent une limite sur la quantité de bande passante disponible pour les appels vocaux et vidéo. Si cette limite de bande passante est atteinte, aucun nouvel appel vocal ou vidéo ne peut être passé tant que l’un des appels en cours n’est pas terminé et libéré les ressources réseau requises.
  
## <a name="accessing-the-call-admission-control-report"></a>Accès au rapport de contrôle d’admission des appels

Le rapport de contrôle d’admission des appels est accessible à partir de la page d’accueil Rapports de surveillance. À partir du rapport de contrôle d’admission des appels, vous pouvez descendre dans l’un des rapports suivants :
  
- Rapport détaillé de conférence : pour accéder à ce rapport, cliquez sur la mesure Détails d’une session de conférence. 
    
- Rapport détaillé de session D’égal à égal : pour accéder à ce rapport, cliquez sur la mesure Détails d’une session d’égal à égal.
    
## <a name="making-the-best-use-of-the-call-admission-control-report"></a>Utilisation du rapport de contrôle d’admission des appels

Pour obtenir la liste des appels qui ont échoué en raison d’une bande passante insuffisante, sélectionnez Appels rejetés en raison du contrôle d’admission des appels dans la liste de listes listes des catégories d’appels. La plupart des appels renvoyés auront probablement un ID de diagnostic de 5 :
  
Bande passante insuffisante pour établir une session. Tentez le ré-itinéraire PSTN.
  
Cela indique que les limitations du contrôle d’admission des appels empêchaient l’appel d’être effectué sur le réseau VoIP.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport de contrôle d’admission des appels vous permet de filtrer les appels par l’utilisateur qui a initié l’appel ou par l’utilisateur qui a été appelé. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.
  
Le tableau suivant répertorie les filtres que vous pouvez utiliser avec le rapport de contrôle d’admission des appels.
  
**Filtres du rapport de contrôle d’admission des appels**

|**Name**|**Description**|
|:-----|:-----|
|**From** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 17/07/12015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/17/12015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/13/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**To** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 17/07/12015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/17/12015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/13/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Pool** <br/> |Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou du serveur Edge. Vous pouvez sélectionner un pool individuel ou cliquer sur **[Tous]** pour afficher les données de tous les pools. Cette liste déroulante est renseignée automatiquement en fonction des enregistrements de la base de données.<br/> |
|**Type d’activité** <br/> | Type d’activité. Sélectionnez l’une des activités suivantes : <br/>  [Tous] <br/>  Pair à pair <br/>  Programme <br/> |
|**Catégorie d’appel** <br/> | Indique la raison pour laquelle le cac a été utilisé pour l’appel. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Appel rejeté en raison du contrôle d’admission des appels <br/>  Appels réacheminés via PSTN en raison du contrôle d’admission des appels <br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a>Mesures pour les sessions d’égal à égal

Le tableau suivant répertorie les informations fournies dans le rapport de contrôle d’admission des appels pour les sessions d’égal à égal (c’est-à-dire, les sessions impliquant seulement deux participants).
  
**Mesures des sessions P2D**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Detail** <br/> |Non  <br/> |Lorsque vous cliquez sur cet élément, le rapport vous présente un rapport détaillé de session P2D pour la session spécifiée.  <br/> |
|**De l’utilisateur** <br/> |Oui  <br/> |Adresse SIP de l’utilisateur ayant initié la session.  <br/> |
|**À l’utilisateur** <br/> |Oui  <br/> |Adresse SIP de l’utilisateur qui a été invité à rejoindre la session.  <br/> |
|**Modalités** <br/> |Oui  <br/> |Modalités de communication (audio et vidéo, par exemple) qui ont été utilisées pendant la session.  <br/> |
|**Heure d’invitation** <br/> |Oui  <br/> |Date et heure d’envoi de l’invitation de session initiale à l’utilisateur De.  <br/> |
|**Heure de réponse** <br/> |Oui  <br/> |Date et heure auxquelles l’acceptation de l’invitation a été reçue.  <br/> |
|**Heure de fin** <br/> |Oui  <br/> |Date et heure de fin de la session.  <br/> |
|**ID de diagnostic** <br/> |Oui  <br/> |Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles au dépannage des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible d’avoir des sessions SIP sans ces en-têtes), et ne sont signalés que pour les sessions ayant rencontré des problèmes d’un type ou d’un autre.  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>Mesures pour les sessions de conférence

Le tableau suivant répertorie les informations fournies dans le rapport de contrôle d’admission des appels pour les sessions de conférence (c’est-à-dire, les sessions impliquant au moins trois participants).
  
**Mesures des sessions de conférence**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**URI de la conférence** <br/> |Oui  <br/> |Identificateur unique de la conférence. Lorsque vous cliquez sur cet élément, le rapport affiche les participants individuels à la conférence.  <br/> |
|**Organizer** <br/> |Oui  <br/> |Adresse SIP de l’utilisateur qui a organisé la conférence.  <br/> |
|**Pool** <br/> |Oui  <br/> |Serveur Edge utilisé dans la conférence.  <br/> |
|**Heure de début** <br/> |Oui  <br/> |Date et heure auxquelles la conférence a commencé.  <br/> |
|**Heure de fin** <br/> |Oui  <br/> |Date et heure de fin de la conférence.  <br/> |
   
## <a name="metrics-for-individual-conference-participants"></a>Mesures pour les participants individuels à la conférence

Le tableau suivant répertorie les informations fournies dans le rapport de contrôle d’admission des appels pour les participants individuels à la conférence.
  
**Mesures pour les participants individuels à la conférence**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Role** <br/> |Non  <br/> |Rôle (par exemple, présentateur) joué par le participant à la conférence.  <br/> |
|**Participant** <br/> |Non  <br/> |Adresse SIP du participant à la conférence.  <br/> |
|**Connectivité** <br/> |Non  <br/> |Connectivité réseau (généralement Depuis interne ou Depuis externe) du participant.  <br/> |
|**Modalité** <br/> |Non  <br/> |Type de conférence (par exemple, conférence A/V).  <br/> |
|**Heure d’arrivée** <br/> |Non  <br/> |Date et heure auxquelles le participant a rejoint la conférence.  <br/> |
|**Heure de départ** <br/> |Non  <br/> |Date et heure auxquelles le participant a quitté la conférence.  <br/> |
|**ID de diagnostic** <br/> |Non  <br/> |Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles au dépannage des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible d’avoir des sessions SIP sans ces en-têtes), et ne sont signalés que pour les sessions ayant rencontré des problèmes d’un type ou d’un autre.  <br/> |
   

