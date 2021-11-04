---
title: Rapport détaillé de session D’égal à égal dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
description: 'Résumé : Découvrez le rapport détaillé de session D’égal à égal dans Skype Entreprise Server.'
ms.openlocfilehash: 6ca45f05c3ee8346c6c6cac5bf5a1845be2d3a20
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774804"
---
# <a name="peer-to-peer-session-detail-report-in-skype-for-business-server"></a>Rapport détaillé de session D’égal à égal dans Skype Entreprise Server
 
**Résumé :** Découvrez le rapport détaillé de session D’égal à égal dans Skype Entreprise Server.
  
Le rapport détaillé de session d’égal à égal retourne des informations détaillées sur une session d’égal à égal. Par exemple, si vous sélectionnez une session de messagerie instantanée, le rapport indique le nombre de messages envoyés par chacun des deux utilisateurs dans la session.
  
## <a name="accessing-the-peer-to-peer-session-detail-report"></a>Accès au rapport détaillé de session d’égal à égal

Vous pouvez accéder au rapport de détails de session d’égal à égal à partir de l’un des rapports suivants (disponibles en totalité dans la page d’accueil Rapports de surveillance) :
  
- Rapport d’inventaire de téléphonie IP
    
- Rapport d’activité de l’utilisateur
    
- Rapport de contrôle d’admission des appels
    
- Rapport de liste des échecs 
    
À partir du rapport détaillé de session P2E, vous pouvez accéder au rapport de diagnostic dans [Skype Entreprise Server](diagnostic-report.md) en cliquant sur la mesure Rapport de diagnostic (détails). Vous pouvez aussi accéder au rapport des principales défaillances en cliquant sur l’une de ces deux mesures :
  
- Réponse
    
- ID de diagnostic
    
## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a>Exploiter au mieux le rapport détaillé de session d’égal à égal

Le rapport détaillé de session d’égal à égal comprend un grand nombre de mesures, dont bon nombre peuvent être inconnues des administrateurs système. Toutefois, dans bien des cas, vous pouvez afficher une info-bulle qui offre une brève description de cette mesure en maintenant simplement votre souris sur l’étiquette de la mesure.
  
Note que les mesures qui apparaissent sur un rapport donné dépendent du type de session d’égal à égal que vous avez sélectionné. Une session audio/vidéo et une session de messagerie instantanée n’affichent pas le même ensemble de mesures.
  
Vous pouvez également pointer votre souris sur les mesures Code de réponse et ID de diagnostic pour obtenir une description de ces valeurs :
  
## <a name="filters"></a>Filtres

Aucun. Vous ne pouvez pas filtrer le Rapport détaillé de session d’égal à égal.
  
## <a name="session-information-metrics"></a>Mesures des informations de session

Le tableau suivant liste les informations fournies dans le Rapport détaillé de session d’égal à égal de chaque session.
  
**Mesures des informations de session**

|**Name**|**Description**|
|:-----|:-----|
|**FQDN du pool** <br/> |Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou serveur Edge impliqué dans la session.  <br/> |
|**Heure d’invitation** <br/> |Date et heure auxquelles l’invitation a été envoyée à l’origine.  <br/> |
|**Heure de réponse** <br/> |Date et heure auxquelles l’acceptation de l’invitation a été reçue.  <br/> |
|**De l’utilisateur** <br/> |Adresse SIP de l’utilisateur qui a initié la session.  <br/> |
|**Agent utilisateur d’origine** <br/> |Logiciel utilisé par le système d’extrémité de l’utilisateur qui a démarré la session.  <br/> |
|**Interne à l’utilisateur d’origine** <br/> |Indique si l’utilisateur qui a initié la session était connecté au réseau interne.  <br/> |
|**Utilisateur d’origine intégré au téléphone de bureau** <br/> |Indique si le système d’extrémité utilisé par l’utilisateur qui a démarré la session est intégré avec son téléphone de bureau.  <br/> |
|**Priorité de la session** <br/> |Priorité assignée à la session. Les priorités valides sont : Inconnu, Non urgent, Normal, Urgent et Urgence.  <br/> |
|**Code de réponse**. <br/> |Code de réponse SIP envoyé lors de l’échec de la session.  <br/> |
|**Frontal** <br/> |Nom du serveur frontal utilisé dans la conférence.  <br/> |
|**Délai de capture** <br/> |Date et heure auxquelles les informations de session ont été enregistrées.  <br/> |
|**Heure de fin** <br/> |Date et heure de fin de la session.  <br/> |
|**À l’utilisateur** <br/> |Adresse SIP de l’utilisateur invité à la session.  <br/> |
|**Agent utilisateur de destination** <br/> |Logiciel utilisé par le système d’extrémité de l’utilisateur qui a été invité à la session.  <br/> |
|**Interne à l’utilisateur de destination** <br/> |Indique si l’utilisateur qui a été invité à la session était connecté au réseau interne.  <br/> |
|**Utilisateur de destination intégré au téléphone de bureau** <br/> |Indique si le système d’extrémité utilisé par l’utilisateur qui a été invité à la session est intégré avec son téléphone de bureau.  <br/> |
|**Nouvelle tentative de session** <br/> |Indique si la session est une nouvelle tentative de session qui a précédemment échoué.  <br/> |
|**ID de diagnostic** <br/> |Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles au dépannage des erreurs. Placez la souris au-dessus du numéro d’ID pour afficher des informations supplémentaires sur cet ID.  <br/> |
   
## <a name="metrics-for-modalities"></a>Mesures des modalités

Le tableau suivant liste les informations fournies dans le Rapport détaillé de session d’égal à égal de chaque modalité de session.
  
**Mesures des modalités**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Modalités** <br/> |Non  <br/> |Modalités utilisées dans la session. Par exemple, messagerie instantanée ou transfert de fichier.  <br/> |
|**Messages de l’expéditeur** <br/> |Non  <br/> |Nombre de messages envoyés par l’utilisateur qui a démarré la session.  <br/> |
|**Messages du destinataire** <br/> |Non  <br/> |Nombre de messages envoyés par l’utilisateur qui a été invité à rejoindre la session.  <br/> |
   
## <a name="metrics-for-diagnostic-reports"></a>Mesures pour les rapports de diagnostic

Le tableau suivant liste les informations fournies dans le Rapport détaillé de session d’égal à égal pour chaque rapport de diagnostic.
  
**Mesures pour les rapports de diagnostic**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Detail** <br/> |Non  <br/> |Lorsque vous cliquez sur cet élément, le rapport montre le rapport de diagnostic pour la session.  <br/> |
|**Heure du rapport** <br/> |Non  <br/> |Date et heure d’enregistrement du rapport.  <br/> |
|**Demande** <br/> |Non  <br/> |Type de demande SIP. Par exemple, INVITE ou BYE.  <br/> |
|**ID de diagnostic** <br/> |Non  <br/> |Identifiant unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui procure souvent des informations utiles à des fins de dépannage.  <br/> |
|**Type de contenu** <br/> |Non  <br/> |Type de contenu multimédia utilisé dans la conférence. Par exemple, Application/sdp est un type de contenu commun. Le protocole SDP (Session Description Protocol) est un protocole Internet standard utilisé pour les annonces de session, les invitations aux sessions et autres formes de démarrage de session multimédia.  <br/> |
|**Auteur du rapport** <br/> |Non  <br/> |Ordinateur (c’est-à-dire, client ou serveur) qui a signalé le problème.  <br/> |
   

