---
title: Skype pour assurer la compatibilité avec les applications Office Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Comprendre les méthodes que vous pouvez accéder à Skype pour les fonctionnalités d’entreprise à partir d’Outlook et d’autres applications Microsoft Office.
ms.openlocfilehash: 2b58c9f8decef9be329dbb3f9e77422b3f0a59c0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype pour assurer la compatibilité avec les applications Office Business
 
Comprendre les méthodes que vous pouvez accéder à Skype pour les fonctionnalités d’entreprise à partir d’Outlook et d’autres applications Microsoft Office.
  
Cette rubrique décrit la compatibilité de Skype pour les entreprises avec des versions différentes des suites de Microsoft Office. 
  
## <a name="office-and-skype-for-business"></a>Office et Skype pour entreprise

Le tableau suivant décrit le Skype pour les fonctionnalités d’entreprise qui sont pris en charge par les différentes versions de Microsoft Office, une fois qu’Exchange est déployé et intégré comme décrit dans [l’Intégration de Skype pour 2015 de serveur d’entreprise avec Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
**Skype pour les entreprises et la compatibilité de Microsoft Office**

|**Fonctionnalité**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 et 2016**|**2016 d’Office pour Mac** & #x 2776 ; |
|:-----|:-----|:-----|:-----|
|**Fonctionnalités d’Outlook** <br/> ||||
|Personnaliser les invitations aux réunions Outlook (ajouter un logo, une URL d’aide, une clause d’exclusion de responsabilité ou un texte de pied de page)  <br/> |Non  <br/> |Oui  <br/> |Non  <br/> |
|Configurer une option de réunion pour désactiver le micro et la vidéo par défaut  <br/> |Non  <br/> |Oui  <br/> |Non  <br/> |
|Magasin de contacts unifiée pour la gestion des listes de Contacts dans Office et Skype pour entreprise  <br/> |Non  <br/> |Oui (nécessite Exchange 2013 ou version supérieure)  <br/> |Oui  <br/> |
|Images de profil haute résolution  <br/> |Non  <br/> |Oui (nécessite Exchange 2013 ou version supérieure)  <br/> |Oui  <br/> |
|Le statut de présence dans le Microsoft Outlook à partir de, à et les champs Cc  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|Répondre avec la messagerie instantanée ou l’appeler à partir du menu de la disponibilité  <br/> |Oui (depuis la carte de visite)  <br/> |Oui (depuis la carte de visite)  <br/> |Oui (depuis la carte de visite)  <br/> |
|Statut de présence dans une demande de réunion sous l’onglet Assistant Planification.  <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|Réponse à l’appel ou messagerie instantanée à partir de la barre d’outils ou le ruban dans un message reçu  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|**Autres applications Office** <br/> ||||
|Notes partagées OneNote  <br/> |Non  <br/> |Oui  <br/> |Non  <br/> |
|Configuration intégrée au programme d’installation d’Office  <br/> |Non  <br/> |Oui  <br/> |Non  <br/> |
|Contenu de présentation PowerPoint  <br/> |Oui  <br/> |Oui  <br/> (VBSS également disponible)  <br/> |Oui  <br/> |
|Messagerie instantanée et présence dans les fichiers Microsoft Word et Microsoft Excel (balises actives activées)  <br/> |Microsoft Word uniquement  <br/> |Microsoft Word uniquement  <br/> |Non  <br/> |
|Messagerie instantanée et présence sur les sites Microsoft SharePoint (Outlook doit être installé)  <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
   
& #x 2776 ; -Suppose que vous avez installé et en cours d’exécution sur le client Mac ou la 2011 Lync pour client Mac un Skype pour les entreprises.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server et Skype pour entreprise

Le tableau suivant décrit les Skype pour la prise en charge de l’entreprise pour les différentes versions d’Exchange Server. Outlook doit être installé sur l’ordinateur client pour traiter les appels d’interface MAPI étendue et certaines fonctionnalités nécessitent l’utilisation d’Exchange Web Services (EWS).
  
**Skype pour les entreprises et la compatibilité d’Exchange Server**

|**Version d’Exchange Server**|**Skype pour la prise en charge de l’entreprise**|
|:-----|:-----|
|Exchange Server 2016  <br/> |Identique à la prise en charge d’Exchange Server 2013  <br/> |
|Exchange Server 2013  <br/> |Identique à la prise en charge d’Exchange Server 2010, avec l’ajout de  <br/>&bull;&nbsp;&nbsp;Magasin de contacts unifiée  <br/>&bull;&nbsp;&nbsp;Images haute résolution  <br/>&bull;&nbsp;&nbsp;Intégration de l’archivage  <br/> **Remarque :** Pour plus d’informations, consultez [Intégration de Skype pour 2015 de serveur d’entreprise avec Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/> |Les fonctionnalités suivantes sont disponibles uniquement par l’intermédiaire d’EWS :  <br/>&bull;&nbsp;&nbsp;Lire ou de supprimer des éléments dans le dossier historique des conversations  <br/>&bull;&nbsp;&nbsp;Lire ou de supprimer des éléments de courrier vocal  <br/>&bull;&nbsp;&nbsp;Afficher les informations de disponibilité étendues et objet de la réunion et l’emplacement  <br/>&bull;&nbsp;&nbsp;Synchronisation de contacts Exchange  <br/> Les dossiers publics sont une option dans Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>Voir aussi
 

[Configuration requise du client Windows et prise en charge des logiciels](windows-requirements.md)
  
[Planifier des clients de réunions (Web App et réunions App)](meetings-clients.md)
#### 

[Interopérabilité du client dans Lync 2013](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)
  
[Configuration requise du client](http://technet.microsoft.com/library/38f3a465-dac1-4381-bc59-270a4ef07ced.aspx)
  
[Spécifications de App Store de Windows de Lync](http://technet.microsoft.com/library/5f2e0a40-8450-4f61-b6f6-913fc1906020.aspx)

