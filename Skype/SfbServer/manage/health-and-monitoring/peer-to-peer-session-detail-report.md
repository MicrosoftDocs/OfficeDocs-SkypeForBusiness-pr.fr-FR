---
title: Rapport détaillé de session d’égal à égal dans Skype entreprise Server
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
ms.assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
description: 'Résumé : en savoir plus sur le rapport de détail de session d’égal à égal dans Skype entreprise Server.'
ms.openlocfilehash: 4c6b05e6e4e4110a43c21dbdbbc7f190ecae98ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817773"
---
# <a name="peer-to-peer-session-detail-report-in-skype-for-business-server"></a>Rapport détaillé de session d’égal à égal dans Skype entreprise Server
 
**Résumé :** En savoir plus sur le rapport de détail de session d’égal à égal dans Skype entreprise Server.
  
Le rapport détaillé de session P2P renvoie des informations détaillées sur une session P2P. Par exemple, si vous sélectionnez une session de messagerie instantanée, le rapport indique le nombre de messages envoyés par chacun des deux utilisateurs dans la session.
  
## <a name="accessing-the-peer-to-peer-session-detail-report"></a>Accès au rapport détaillé de session P2P

Vous pouvez accéder au rapport de détails de session P2P à partir de l’un des rapports suivants (disponibles en totalité dans la page d’accueil Rapports de surveillance) :
  
- Rapport d’inventaire de téléphonie IP
    
- Rapport d’activité de l’utilisateur
    
- Rapport de contrôle d’admission des appels
    
- Rapport de liste des échecs 
    
Dans le rapport Détails de la session d’égal à égal, vous pouvez accéder au [rapport de diagnostic dans Skype entreprise Server](diagnostic-report.md) en cliquant sur le rapport de diagnostic (détails). Vous pouvez aussi accéder au rapport des principales défaillances en cliquant sur l’une de ces deux mesures :
  
- Réponse
    
- ID de diagnostic
    
## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a>Exploiter au mieux le rapport détaillé de session P2P

Le rapport détaillé de session P2P comprend un grand nombre de mesures, dont bon nombre peuvent être inconnues des administrateurs système. Cependant, dans bien des cas, vous pouvez afficher une info-bulle qui offre une brève description de cette mesure en maintenant simplement votre souris sur l’étiquette de la mesure.
  
Note que les mesures qui s’affichent sur un rapport donné dépendent du type de session P2P que vous avez sélectionné. Une session audio/vidéo et une session de messagerie instantanée n’affichent pas le même ensemble de mesures.
  
Vous pouvez également pointer votre souris sur les mesures Code de réponse et ID de diagnostic pour obtenir une description de ces valeurs :
  
## <a name="filters"></a>Filtres

Aucun. Vous ne pouvez pas filtrer le Rapport détaillé de session P2P.
  
## <a name="session-information-metrics"></a>Mesures des informations de session

Le tableau ci-dessous liste les informations fournies dans le Rapport détaillé de session P2P de chaque session.
  
**Mesures des informations de session**

|**Nom**|**Description**|
|:-----|:-----|
|**FQDN du pool** <br/> |Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou serveur Edge impliqué dans la session.  <br/> |
|**Heure d’invitation** <br/> |Date et heure auxquelles l’invitation a été envoyée à l’origine.  <br/> |
|**Heure de réponse** <br/> |Date et heure auxquelles l’acceptation de l’invitation a été reçue.  <br/> |
|**De l’utilisateur** <br/> |Adresse SIP de l’utilisateur ayant initié la session.  <br/> |
|**Agent utilisateur d’origine** <br/> |Logiciel utilisé par le point de terminaison de l’utilisateur ayant initié la session.  <br/> |
|**Interne à l’utilisateur d’origine** <br/> |Indique si l’utilisateur qui a initié la session était connecté au réseau interne.  <br/> |
|**Utilisateur d’origine intégré au téléphone de bureau** <br/> |Indique si le point de terminaison utilisé par l’utilisateur qui a démarré la session est intégré à son téléphone de bureau.  <br/> |
|**Priorité de la session** <br/> |Priorité affectée à la session. Les priorités valides sont : Inconnu, Non urgent, Normal, Urgent et Urgence.  <br/> |
|**Code de réponse** <br/> |Code de réponse SIP envoyé lors de l’échec de session.  <br/> |
|**Serveur frontal** <br/> |Nom du serveur frontal utilisé dans la conférence.  <br/> |
|**Délai de capture** <br/> |Date et heure auxquelles les informations de session ont été enregistrées.  <br/> |
|**Heure de fin** <br/> |Date et heure de fin de la session.  <br/> |
|**À l’utilisateur** <br/> |Adresse IP de l’utilisateur ayant été invité à participer à la session.  <br/> |
|**Agent utilisateur de destination** <br/> |Logiciel utilisé par le point de terminaison de l’utilisateur qui a été invité à la session.  <br/> |
|**Interne à l’utilisateur de destination** <br/> |Indique si l’utilisateur qui a été invité à la session était connecté au réseau interne.  <br/> |
|**Utilisateur de destination intégré au téléphone de bureau** <br/> |Indique si le point de terminaison utilisé par l’utilisateur qui a été invité à la session est intégré à son téléphone de bureau.  <br/> |
|**Nouvelle tentative de session** <br/> |Indique si la session est une nouvelle tentative de session qui a précédemment échoué.  <br/> |
|**ID de diagnostic** <br/> |Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles à l’identification et à la résolution des erreurs. Placez la souris au-dessus du numéro d’ID pour afficher des informations supplémentaires sur cet ID.  <br/> |
   
## <a name="metrics-for-modalities"></a>Mesures des modalités

Le tableau ci-dessous liste les informations fournies dans le Rapport détaillé de session P2P de chaque modalité de session.
  
**Mesures des modalités**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Modalités** <br/> |Non  <br/> |Modalités utilisées dans la session. Par exemple, messagerie instantanée ou transfert de fichier.  <br/> |
|**Messages de l’expéditeur** <br/> |Non  <br/> |Nombre de messages envoyés par l’utilisateur qui a démarré la session.  <br/> |
|**Messages du destinataire** <br/> |Non  <br/> |Nombre de messages envoyés par l’utilisateur qui a été invité à rejoindre la session.  <br/> |
   
## <a name="metrics-for-diagnostic-reports"></a>Mesures pour les rapports de diagnostic

Le tableau ci-dessous liste les informations fournies dans le Rapport détaillé de session P2P pour chaque rapport de diagnostic.
  
**Mesures pour les rapports de diagnostic**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Détails** <br/> |Non  <br/> |Lorsque vous cliquez sur cet élément, le rapport montre le rapport de diagnostic pour la session.  <br/> |
|**Heure du rapport** <br/> |Non  <br/> |Date et heure d’enregistrement du rapport.  <br/> |
|**Demande** <br/> |Non  <br/> |Type de demande SIP. Par exemple, INVITE ou BYE.  <br/> |
|**ID de diagnostic** <br/> |Non  <br/> |Identificateur unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui fournit souvent des informations utiles pour résoudre des erreurs.  <br/> |
|**Type de contenu** <br/> |Non  <br/> |Type de contenu multimédia utilisé dans la conférence. Par exemple, Application/sdp est un type de contenu commun. Le protocole SDP (Session Description Protocol) est un protocole Internet standard utilisé pour les annonces de session, les invitations aux sessions et autres formes de démarrage de session multimédia.  <br/> |
|**Auteur du rapport** <br/> |Non  <br/> |Ordinateur (c’est-à-dire, client ou serveur) qui a signalé le problème.  <br/> |
   

