---
title: Appel de rapport de contrôle d’admission des appels dans Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
description: 'Résumé : Découvrez les rapports de contrôle de d’admission des appels utilisés dans Skype pour Business Server.'
ms.openlocfilehash: c3828eb890ed8f70c41bc669785278f9be017893
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21011245"
---
# <a name="call-admission-control-report-in-skype-for-business-server"></a>Appel de rapport de contrôle d’admission des appels dans Skype pour Business Server
 
**Résumé :** Découvrez les rapports de contrôle de d’admission des appels utilisés dans Skype pour Business Server.
  
Le rapport du contrôle d’admission des appels fournit des informations sur les sessions P2P et de conférence menées avec des restrictions mises en place par le contrôle d’admission des appels. Celui-ci offre la possibilité aux administrateurs d’autoriser (ou non) les sessions de communication en fonction des restrictions de bande passante. Par exemple, les administrateurs peuvent créer des stratégies qui imposent une quantité limite de bande passante disponible pour les appels vocaux et vidéo. Si cette limite est atteinte, aucun nouvel appel vocal ou vidéo ne peut être effectué tant que l’un des appels en cours n’est pas terminé et que les ressources réseau requises ne sont pas libérées.
  
## <a name="accessing-the-call-admission-control-report"></a>Accès au rapport du contrôle d’admission des appels

Le rapport du contrôle d’admission des appels est accessible à partir de la page d’accueil des Rapports de suivi. De ce rapport, vous pouvez atteindre l’un des rapports suivants :
  
- Rapport détaillé de conférence - pour accéder à ce rapport, cliquez sur la mesure détails à partir d’une session de conférence. 
    
- Rapport de détaillé de Session d’égal à égal - pour accéder à ce rapport, cliquez sur la mesure détails d’une session d’égal à égal.
    
## <a name="making-the-best-use-of-the-call-admission-control-report"></a>Utilisation optimale du rapport du contrôle d’admission des appels

Pour obtenir une liste des appels ayant échoué en raison d’une bande passante insuffisante, sélectionnez Appels rejetés en raison du contrôle d’admission des appels dans la liste déroulante Catégorie d’appel. La plupart des appels renvoyés auront probablement un ID de diagnostic de 5 :
  
Bande passante insuffisante pour établir une session. Essayez le réacheminement RTC.
  
Cela indique que les limitations du contrôle d’admission des appels empêchaient l’appel d’être effectué sur le réseau VoIP.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport de contrôle d’admission des appels vous permet de filtrer des appels en fonction de l’utilisateur qui les a émis ou qui a été appelé. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.
  
Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de contrôle d’admission des appels.
  
**Filtres du rapport de contrôle d’admission des appels**

|**Nom**|**Description**|
|:-----|:-----|
|**De** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 17/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 17/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 13/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**À** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 17/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 17/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 13/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Pool** <br/> |Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur **[Tous]** pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.<br/> |
|**Type d’activité** <br/> | Type d’activité. Sélectionnez l’une des activités suivantes : <br/>  [Tous] <br/>  P2P <br/>  Conférence <br/> |
|**Catégorie d’appel** <br/> | Indique la raison pour laquelle le contrôle d’admission des appels a été utilisé pour l’appel. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Appels rejetés en raison du contrôle d’admission des appels <br/>  Appels réacheminés via RTC en raison du contrôle d’admission des appels <br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a>Mesures pour les sessions P2P

Le tableau ci-dessous répertorie les informations fournies par le rapport de contrôle d’admission des appels pour les sessions P2P (c’est-à-dire, les sessions qui n’impliquent que deux participants).
  
**Mesures pour les sessions P2P**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Détails** <br/> |Non  <br/> |Lorsque vous cliquez sur cet élément, le rapport présente un rapport détaillé de session P2P pour la session spécifiée.  <br/> |
|**De l’utilisateur** <br/> |Oui  <br/> |Adresse SIP de l’utilisateur ayant initié la session.  <br/> |
|**À l’utilisateur** <br/> |Oui  <br/> |Adresse SIP de l’utilisateur qui a été invité à participer à la session.  <br/> |
|**Modalités** <br/> |Oui  <br/> |Modalités de communication (audio et vidéo) qui ont été utilisées pendant la session.  <br/> |
|**Heure d’invitation** <br/> |Oui  <br/> |Date et heure auxquelles l’invitation initiale à la session a été envoyée à l’utilisateur.  <br/> |
|**Heure de réponse** <br/> |Oui  <br/> |Date et heure auxquelles l’acceptation de l’invitation a été reçue.  <br/> |
|**Heure de fin** <br/> |Oui  <br/> |Date et heure auxquelles la session s’est terminée.  <br/> |
|**ID de diagnostic** <br/> |Oui  <br/> |Identificateur unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui fournit souvent des informations utiles pour résoudre des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible que des sessions SIP n’incluent pas ces en-têtes) et les ID de diagnostic sont uniquement signalés pour les sessions qui ont rencontré des problèmes, quels qu’ils soient.  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>Mesures pour les sessions de conférence

Le tableau ci-dessous répertorie les informations fournies par le rapport de contrôle d’admission des appels pour les sessions de conférence (c’est-à-dire, les sessions qui impliquent trois participants ou plus).
  
**Mesures pour les sessions de conférence**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**URI de la conférence** <br/> |Oui  <br/> |Identificateur unique de la conférence. Lorsque vous cliquez sur cet élément, le rapport présente les participants individuels de la conférence.  <br/> |
|**Organisateur** <br/> |Oui  <br/> |Adresse SIP de l’utilisateur qui a organisé la conférence.  <br/> |
|**Pool** <br/> |Oui  <br/> |Serveur Edge utilisé pour la conférence.  <br/> |
|**Heure de début** <br/> |Oui  <br/> |Date et heure auxquelles la conférence a commencé.  <br/> |
|**Heure de fin** <br/> |Oui  <br/> |Date et heure de fin de la conférence.  <br/> |
   
## <a name="metrics-for-individual-conference-participants"></a>Mesures pour les participants individuels de la conférence

Le tableau qui suit répertorie les informations fournies dans le rapport de contrôle d’admission des appels pour chaque participant d’une conférence.
  
**Mesures pour les participants individuels de la conférence**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Rôle** <br/> |Non  <br/> |Rôle (par exemple, présentateur) joué par le participant à la conférence.  <br/> |
|**Participant** <br/> |Non  <br/> |Adresse SIP du participant à la conférence.  <br/> |
|**Connectivité** <br/> |Non  <br/> |Connectivité réseau (généralement Depuis interne ou Depuis externe) du participant.  <br/> |
|**Modalité** <br/> |Non  <br/> |Type de conférence (par exemple, conférence A/V).  <br/> |
|**Heure d’arrivée** <br/> |Non  <br/> |Date et heure auxquelles le participant a rejoint la conférence.  <br/> |
|**Heure de départ** <br/> |Non  <br/> |Date et heure auxquelles le participant a quitté la conférence.  <br/> |
|**ID de diagnostic** <br/> |Non  <br/> |Identificateur unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui fournit souvent des informations utiles pour résoudre des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible que des sessions SIP n’incluent pas ces en-têtes) et les ID de diagnostic sont uniquement signalés pour les sessions qui ont rencontré des problèmes, quels qu’ils soient.  <br/> |
   

