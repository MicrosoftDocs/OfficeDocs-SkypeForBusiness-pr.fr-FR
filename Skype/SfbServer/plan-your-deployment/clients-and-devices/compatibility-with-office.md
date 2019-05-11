---
title: Skype pour assurer la compatibilité avec les applications Office Business
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Comprendre les méthodes que vous pouvez accéder à Skype pour les fonctionnalités d’Outlook et d’autres applications Microsoft Office.
ms.openlocfilehash: f8f6f31e6b77b50178bf80210606ca5b92ea4e05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33923854"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype pour assurer la compatibilité avec les applications Office Business
 
Comprendre les méthodes que vous pouvez accéder à Skype pour les fonctionnalités d’Outlook et d’autres applications Microsoft Office.
  
Cette rubrique décrit la compatibilité de Skype pour les entreprises avec différentes versions des suites Microsoft Office. 
  
## <a name="office-and-skype-for-business"></a>Office et Skype pour les entreprises

Le tableau suivant décrit le Skype pour les fonctionnalités qui sont prises en charge par les différentes versions d’Office, une fois que Exchange est déployé et intégré comme indiqué dans [l’Intégration de Skype pour Business Server avec Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
**Skype pour les entreprises et de compatibilité Microsoft Office**

|**Fonctionnalité**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 et 2016**|_AMP_ **2016 Office pour Mac** #x 2776 ; |
|:-----|:-----|:-----|:-----|
|**Fonctionnalités Outlook** ||||
|Personnaliser les invitations aux réunions Outlook (ajouter un logo, une URL d’aide, une clause d’exclusion de responsabilité ou un texte de pied de page)  |Non  |Oui    |Oui|
|Configurer une option de réunion pour désactiver le micro et la vidéo par défaut    |Non    |Oui    |Non    |
|Magasin de contacts unifié pour la gestion des listes de Contacts dans Office et Skype pour les entreprises    |Non    |Oui (nécessite Exchange 2013 ou version supérieure)    |Oui    |
|Images de profil haute résolution    |Non    |Oui (nécessite Exchange 2013 ou version supérieure)    |Oui    |
|Statut de présence dans le Microsoft Outlook à partir de, à et Cc champs    |Oui     |Oui     |Oui    |
|Répondre avec la messagerie instantanée ou un appel à partir du menu disponibilité    |Oui (depuis la carte de visite)    |Oui (depuis la carte de visite)    |Oui (depuis la carte de visite)    |
|Statut de présence dans une demande de réunion sous l’onglet Assistant Planification.    |Oui     |Oui    |Non    |
|Répondre par messagerie instantanée ou un appel à partir de la barre d’outils ou le ruban dans un message électronique reçu    |Oui     |Oui     |Oui    |
|**Autres applications Office**   ||||
|Notes partagées OneNote    |Non    |Oui    |Non    |
|Configuration intégrée au programme d’installation d’Office    |Non    |Oui    |Non    |
|Contenu de présentation PowerPoint    |Oui    |Oui (VBSS également disponible)    |Oui    |
|Messagerie instantanée et présence dans les fichiers Microsoft Word et Microsoft Excel (balises actives activées)    |Microsoft Word uniquement    |Microsoft Word uniquement    |Non    |
|Messagerie instantanée et présence sur les sites Microsoft SharePoint (Outlook doit être installé)    |Oui    |Oui    |Non    |
   
& #x 2776 ; -Suppose que vous avez installé et qui sont en cours d’exécution sur le client Mac ou le Lync 2011 pour le client Mac un Skype pour les entreprises.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server et Skype pour les entreprises

Le tableau suivant décrit Skype pour la prise en charge de l’entreprise pour les différentes versions d’Exchange Server. Outlook doit être installé sur l’ordinateur client pour traiter les appels d’interface MAPI étendue et certaines fonctionnalités nécessitent l’utilisation d’Exchange Web Services (EWS).
  
**Skype pour les entreprises et la compatibilité d’Exchange Server**

|**Version d’Exchange Server**|**Skype pour la prise en charge de l’entreprise**|
|:-----|:-----|
|Exchange Server 2019 (Skype pour Business Server 2019 uniquement) |Identique à la prise en charge d’Exchange Server 2013    |
|Exchange Server 2016    |Identique à la prise en charge d’Exchange Server 2013  <br/> |
|Exchange Server 2013  <br/> |Identique à la prise en charge de Microsoft Exchange Server 2010, avec l’ajout de  <br/>&bull;&nbsp;&nbsp;Magasin de contacts unifié  <br/>&bull;&nbsp;&nbsp;Photos haute résolution  <br/>&bull;&nbsp;&nbsp;Intégration d’archivage  <br/> **Remarque :** Pour plus d’informations, voir [Intégration de Skype pour Business Server avec Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/>(Skype pour Business Server 2015 uniquement) |Les fonctionnalités suivantes sont disponibles uniquement par l’intermédiaire d’EWS :  <br/>&bull;&nbsp;&nbsp;Lire ou supprimer des éléments dans le dossier historique des conversations  <br/>&bull;&nbsp;&nbsp;Lire ou supprimer des messages vocaux  <br/>&bull;&nbsp;&nbsp;Afficher les informations de disponibilité étendues et objet de la réunion et l’emplacement  <br/>&bull;&nbsp;&nbsp;Synchronisation des contacts Exchange  <br/> Les dossiers publics sont une option dans Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>Voir aussi
 
[Configuration requise des clients Windows et prise en charge logicielle](windows-requirements.md)
  
[Planifier pour les clients de réunions (application Web et application de réunions)](meetings-clients.md)

