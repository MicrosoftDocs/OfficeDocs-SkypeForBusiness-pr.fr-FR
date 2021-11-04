---
title: Skype Entreprise compatibilité avec Office applications
ms.author: v-mahoffman
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Comprendre les façons dont vous pouvez accéder Skype Entreprise fonctionnalités à partir de Outlook et d’autres applications Microsoft Office applications.
ms.openlocfilehash: e4b826cf6ba79b8db31ec5dec57c8d6bfca5280f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773564"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype Entreprise compatibilité avec Office applications
 
Comprendre les façons dont vous pouvez accéder Skype Entreprise fonctionnalités à partir de Outlook et d’autres applications Microsoft Office applications.
  
Cette rubrique décrit la compatibilité des Skype Entreprise avec différentes versions de Microsoft Office suites. 
  
## <a name="office-and-skype-for-business"></a>Office et Skype Entreprise

Le tableau suivant décrit les fonctionnalités Skype Entreprise qui sont pris en charge par différentes versions de Office une fois que Exchange est déployé et intégré comme décrit dans Intégrer Skype Entreprise Server à [Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
**Skype Entreprise et Microsoft Office compatibilité**

|**Fonctionnalité**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 et 2016**|**Office 2016 pour Mac** &#x2776; |
|:-----|:-----|:-----|:-----|
|**Outlook fonctionnalités** ||||
|Personnaliser Outlook invitations aux réunions (ajouter un logo, une URL d’aide, une clause d’exclusion de responsabilité, un texte de pied de page)  |Non  |Oui   |Oui|
|Configurer l’option de réunion pour désactiver le son et la vidéo des participants par défaut    |Non    |Oui    |Non    |
|Magasin de contacts unifié pour la gestion des listes de contacts Office et Skype Entreprise    |Non    |Oui (nécessite Exchange 2013 ou ultérieure)    |Oui    |
|Images de profil haute résolution    |Non    |Oui (nécessite Exchange 2013 ou ultérieure)    |Oui    |
|Statut de présence dans les champs Microsoft Outlook De, À et Cc    |Oui    |Oui    |Oui    |
|Répondre par messagerie instantanée ou appel à partir du menu de disponibilité    |Oui (à partir de la carte de visite)    |Oui (à partir de la carte de visite)    |Oui (à partir de la carte de visite)    |
|Statut de présence dans une demande de réunion sous l’onglet Assistant Planification.    |Oui    |Oui    |Non    |
|Répondre par messagerie instantanée ou appel à partir de la barre d’outils ou du ruban dans un message électronique reçu    |Oui    |Oui    |Oui    |
|**Autres applications Office de messagerie**   ||||
|OneNote notes partagées    |Non    |Oui    |Non    |
|Programme d’installation intégré au programme Office’installation    |Non    |Oui    |Non    |
|PowerPoint présentation    |Oui    |Oui (VBSS également disponible)    |Oui    |
|Messagerie instantanée et présence dans les fichiers Microsoft Word et Microsoft Excel (balises actives activées)    |Microsoft Word uniquement    |Microsoft Word uniquement    |Non    |
|Messagerie instantanée et présence sur les sites Microsoft SharePoint (Outlook doit être installé)    |Oui    |Oui    |Non    |
   
&#x2776; : suppose que vous avez installé et que vous exécutez actuellement un client Skype Entreprise sur Mac ou le client Lync 2011 pour Mac.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server et Skype Entreprise

Le tableau suivant décrit Skype Entreprise prise en charge de différentes versions de Exchange Server. Outlook doit être installé sur l’ordinateur client pour traiter les appels d’interface MAPI étendue et certaines fonctionnalités nécessitent l’utilisation d’Exchange Web Services (EWS).
  
**Skype Entreprise et Exchange Server compatibilité**

|**Version d’Exchange Server**|**Skype Entreprise prise en charge**|
|:-----|:-----|
|Exchange Server 2019 (Skype Entreprise Server 2019 uniquement) |Identique à Exchange Server 2013    |
|Exchange Server 2016    |Identique à Exchange Server 2013  <br/> |
|Exchange Server 2013  <br/> |Identique à Exchange Server 2010, avec l’ajout de  <br/>&bull;&nbsp;&nbsp;Magasin de contacts unifié  <br/>&bull;&nbsp;&nbsp;Images haute résolution  <br/>&bull;&nbsp;&nbsp;Intégration de l’archivage  <br/> **Remarque :** Pour plus d’informations, [voir Intégrer Skype Entreprise Server avec Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/>(Skype Entreprise Server 2015 uniquement) |Les fonctionnalités suivantes sont disponibles uniquement par l’intermédiaire d’EWS :  <br/>&bull;&nbsp;&nbsp;Lire ou supprimer des éléments dans le dossier Historique des conversations  <br/>&bull;&nbsp;&nbsp;Lire ou supprimer des éléments de messagerie vocale  <br/>&bull;&nbsp;&nbsp;Afficher des informations de libre/occupé étendues, l’objet et l’emplacement de la réunion  <br/>&bull;&nbsp;&nbsp;Exchange synchronisation des contacts  <br/> Les dossiers publics sont facultatifs Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>Voir aussi
 
[Windows client et prise en charge des logiciels](windows-requirements.md)
  
[Planifier les clients Meetings (application Web et application réunions)](meetings-clients.md)

