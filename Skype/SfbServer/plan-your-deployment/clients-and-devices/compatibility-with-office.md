---
title: Compatibilité de Skype entreprise avec les applications Office
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Découvrez les différentes façons d’accéder aux fonctionnalités de Skype entreprise à partir d’Outlook et d’autres applications Microsoft Office.
ms.openlocfilehash: e91174850cb82d325eb9a3f75577d3aaeb3b90f6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803684"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Compatibilité de Skype entreprise avec les applications Office
 
Découvrez les différentes façons d’accéder aux fonctionnalités de Skype entreprise à partir d’Outlook et d’autres applications Microsoft Office.
  
Cette rubrique décrit la compatibilité de Skype entreprise avec différentes versions de la suite Microsoft Office. 
  
## <a name="office-and-skype-for-business"></a>Office et Skype entreprise

Le tableau suivant décrit les fonctionnalités de Skype entreprise prises en charge par les différentes versions d’Office une fois qu’Exchange est déployé et intégré comme décrit dans [intégration de Skype entreprise Server à Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
**Compatibilité avec Skype entreprise et Microsoft Office**

|**Fonctionnalité**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 et 2016**|&#x2776; **Office 2016 pour Mac** |
|:-----|:-----|:-----|:-----|
|**Fonctionnalités Outlook** ||||
|Personnaliser les invitations aux réunions Outlook (ajouter un logo, une URL d’aide, une clause d’exclusion de responsabilité ou un texte de pied de page)  |Non  |Oui   |Oui|
|Configurer une option de réunion pour désactiver le micro et la vidéo par défaut    |Non    |Oui    |Non    |
|Magasin de contacts unifié pour gérer les listes de contacts dans Office et Skype entreprise    |Non    |Oui (nécessite Exchange 2013 ou version supérieure)    |Oui    |
|Images de profil haute résolution    |Non    |Oui (nécessite Exchange 2013 ou version supérieure)    |Oui    |
|Statut de présence dans les champs Microsoft Outlook de, à et CC    |Oui     |Oui     |Oui     |
|Répondre par un message instantané ou un appel dans le menu de disponibilité    |Oui (depuis la carte de visite)    |Oui (depuis la carte de visite)    |Oui (depuis la carte de visite)    |
|Statut de présence dans une demande de réunion sous l’onglet Assistant Planification.    |Oui     |Oui    |Non    |
|Répondre par un message instantané ou un appel à partir de la barre d’outils ou du ruban dans un message électronique reçu    |Oui     |Oui     |Oui     |
|**Autres applications Office**   ||||
|Notes partagées OneNote    |Non    |Oui    |Non    |
|Configuration intégrée au programme d’installation d’Office    |Non    |Oui    |Non    |
|Contenu de présentation PowerPoint    |Oui    |Oui (VBSS également disponible)    |Oui    |
|Messagerie instantanée et présence dans les fichiers Microsoft Word et Microsoft Excel (balises actives activées)    |Microsoft Word uniquement    |Microsoft Word uniquement    |Non    |
|Messagerie instantanée et présence sur les sites Microsoft SharePoint (Outlook doit être installé)    |Oui    |Oui    |Non    |
   
&#x2776;-suppose que vous avez installé et que vous exécutez actuellement un client Skype entreprise sur Mac ou le client Lync 2011 pour Mac.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server et Skype entreprise

Le tableau suivant décrit la prise en charge de Skype entreprise pour différentes versions d’Exchange Server. Outlook doit être installé sur l’ordinateur client pour traiter les appels d’interface MAPI étendue et certaines fonctionnalités nécessitent l’utilisation d’Exchange Web Services (EWS).
  
**Compatibilité avec Skype entreprise et Exchange Server**

|**Version d’Exchange Server**|**Support Skype entreprise**|
|:-----|:-----|
|Exchange Server 2019 (Skype entreprise Server 2019 uniquement) |Identique à la prise en charge d’Exchange Server 2013    |
|Exchange Server 2016    |Identique à la prise en charge d’Exchange Server 2013  <br/> |
|Exchange Server 2013  <br/> |Comme la prise en charge d’Exchange Server 2010, en plus de  <br/>&bull;&nbsp;&nbsp;Magasin de contacts unifié  <br/>&bull;&nbsp;&nbsp;Images haute résolution  <br/>&bull;&nbsp;&nbsp;Intégration de l’archivage  <br/> **Remarque :** Pour plus d’informations, reportez-vous à la rubrique [intégration de Skype entreprise Server à Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/>(Skype entreprise Server 2015 uniquement) |Les fonctionnalités suivantes sont disponibles uniquement par l’intermédiaire d’EWS :  <br/>&bull;&nbsp;&nbsp;Lecture ou suppression d’éléments dans le dossier historique des conversations  <br/>&bull;&nbsp;&nbsp;Lecture ou suppression d’éléments de messagerie vocale  <br/>&bull;&nbsp;&nbsp;Afficher les informations de disponibilité étendues et l’objet et l’emplacement de la réunion  <br/>&bull;&nbsp;&nbsp;Synchronisation de contacts Exchange  <br/> Les dossiers publics sont une option dans Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>Voir aussi
 
[Configuration requise pour le client Windows et prise en charge logicielle](windows-requirements.md)
  
[Planifier pour les clients de conférences (application Web et application réunions)](meetings-clients.md)

