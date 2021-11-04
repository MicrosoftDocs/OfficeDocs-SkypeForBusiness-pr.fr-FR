---
title: Rapport de diagnostic dans Skype Entreprise Server
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
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: 'Résumé : Découvrez le rapport de diagnostic dans Skype Entreprise Server.'
ms.openlocfilehash: 84274659a45d33a144324334cec8b9f1b25c471b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740630"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a>Rapport de diagnostic dans Skype Entreprise Server
 
**Résumé :** Découvrez le rapport de diagnostic dans Skype Entreprise Server.
  
Le Rapport de diagnostic fournit des informations de diagnostic et de dépannage pour les sessions ayant échoué. Ces informations incluent à la fois l’ID de diagnostic et l’en-tête de diagnostic qui ont été signalés lorsque la session a échoué. L’ID de diagnostic est un identificateur unique (sous la forme d’un en-tête ms-diagnostics) qui est joint à un message SIP, tandis que l’en-tête de diagnostic fournit une description d’accompagnement pour l’ID de diagnostic. Ce rapport peut également contenir des informations de dépannage précieuses qui sont connues par le composant de rapport. Par exemple :
  
- Code de motif fourni par la passerelle PSTN qui a généré la défaillance. Quand un appel sortant échoue sur le réseau téléphonique commuté, un code de motif de la « partie Usager RNIS » (ISUP) est automatiquement généré. Par exemple, une passerelle PSTN peut retourner le code de motif 34, indiquant ainsi qu’aucun circuit ou canal n’était disponible pour terminer l’appel.
    
- Nom de domaine complet (FQDN), port et erreurs Winsock de l’homologue pour les échecs de connectivité.
    
- Noms recherchés pour les échecs de résolution DNS. La résolution DNS a lieu chaque fois qu’un client contacte un serveur de noms et demande l’adresse IP correspondant au nom du périphérique spécifié
    
## <a name="accessing-the-diagnostic-report"></a>Accès au Rapport de diagnostic

Le rapport de diagnostic est accessible en cliquant sur la mesure Rapport de diagnostic (détail) dans le rapport détaillé de [session D’égal](peer-to-peer-session-detail-report.md) à égal dans Skype Entreprise Server ou le rapport détaillé de conférence.
  
## <a name="filters"></a>Filtres

Aucun. Il est impossible de filtrer le rapport de diagnostic.
  
## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de diagnostic pour chaque session.
  
**Mesures du rapport de diagnostic**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Heure du rapport** <br/> |Non  <br/> |Date et heure d’enregistrement du rapport.  <br/> |
|**Code de réponse** <br/> |Non  <br/> |Code de réponse SIP envoyé lors de l’échec de session.  <br/> |
|**Type de demande** <br/> |Non  <br/> |Type de demande SIP ayant échoué. Par exemple, INVITE, BYE ou SERVICE.  <br/> |
|**Source** <br/> |Non  <br/> |Source de l’erreur.  <br/> |
|**URI de l’utilisateur d’origine** <br/> |Non  <br/> |Adresse SIP de l’utilisateur ayant initié la session.  <br/> |
|**Agent utilisateur d’origine** <br/> |Non  <br/> |Logiciel utilisé par le point de terminaison de l’utilisateur ayant initié la session.  <br/> |
|**ID de diagnostic** <br/> |Non  <br/> |Identifiant unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui procure souvent des informations utiles à des fins de dépannage.  <br/> |
|**Type de contenu** <br/> |Non  <br/> |Type de contenu multimédia ayant échoué. Par exemple, un type de contenu courant est Application/sdp. Session Description Protocol (SDP) est un protocole Internet standard utilisé pour les annonces de session, les invitations de session et autres formes d’initiation de session multimédia.  <br/> |
|**Application** <br/> |Non  <br/> |Application impliquée dans l’erreur.  <br/> |
|**URI de l’utilisateur de destination** <br/> |Non  <br/> |Adresse IP de l’utilisateur ayant été invité à participer à la session.  <br/> |
|**Temps de connexion à la conférence (ms)** <br/> |Non  <br/> |Temps (en millisecondes) utilisé pour que l’utilisateur rejoigne la conférence.  <br/> |
|**En-tête de diagnostic** <br/> |Non  <br/> |Description de l’ID de diagnostic.  <br/> |
   
La liste des erreurs de diagnostic se trouve dans la [page En-tête Ms-Diagnostics.](/openspecs/office_protocols/ms-ocer/f6787b39-0842-43ca-94a2-6afadda5f0a3)
