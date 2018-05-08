---
title: Skype pour assurer la compatibilité avec les applications Office Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Comprendre les méthodes que vous pouvez accéder à Skype pour les fonctionnalités d’Outlook et d’autres applications Microsoft Office.
ms.openlocfilehash: 186b8951718e6903ec7cc4f8c317504b74917716
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype pour assurer la compatibilité avec les applications Office Business
 
Comprendre les méthodes que vous pouvez accéder à Skype pour les fonctionnalités d’Outlook et d’autres applications Microsoft Office.
  
Cette rubrique décrit la compatibilité de Skype pour les entreprises avec différentes versions des suites Microsoft Office. 
  
## <a name="office-and-skype-for-business"></a>Office et Skype pour les entreprises

Le tableau suivant décrit le Skype pour les fonctionnalités qui sont prises en charge par les différentes versions d’Office, une fois que Exchange est déployé et intégré comme indiqué dans [l’Intégration de Skype pour Business Server 2015 avec Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
**Skype pour les entreprises et de compatibilité Microsoft Office**

|**Fonctionnalité**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 et 2016**|**2016 Office pour Mac** & #x 2776 ; |
|:-----|:-----|:-----|:-----|
|**Fonctionnalités d’Outlook** <br/> ||||
|Personnaliser les invitations aux réunions Outlook (ajouter un logo, une URL d’aide, une clause d’exclusion de responsabilité ou un texte de pied de page)  <br/> |Non  <br/> |Oui  <br/> |Non  <br/> |
|Configurer une option de réunion pour désactiver le micro et la vidéo par défaut  <br/> |Non  <br/> |Oui  <br/> |Non  <br/> |
|Magasin de contacts unifié pour la gestion des listes de Contacts dans Office et Skype pour les entreprises  <br/> |Non  <br/> |Oui (nécessite Exchange 2013 ou version supérieure)  <br/> |Oui  <br/> |
|Images de profil haute résolution  <br/> |Non  <br/> |Oui (nécessite Exchange 2013 ou version supérieure)  <br/> |Oui  <br/> |
|Statut de présence dans le Microsoft Outlook à partir de, à et Cc champs  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|Répondre avec la messagerie instantanée ou un appel à partir du menu disponibilité  <br/> |Oui (depuis la carte de visite)  <br/> |Oui (depuis la carte de visite)  <br/> |Oui (depuis la carte de visite)  <br/> |
|Statut de présence dans une demande de réunion sous l’onglet Assistant Planification.  <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|Répondre par messagerie instantanée ou un appel à partir de la barre d’outils ou le ruban dans un message électronique reçu  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|**Autres applications Office** <br/> ||||
|Notes partagées OneNote  <br/> |Non  <br/> |Oui  <br/> |Non  <br/> |
|Configuration intégrée au programme d’installation d’Office  <br/> |Non  <br/> |Oui  <br/> |Non  <br/> |
|Contenu de présentation PowerPoint  <br/> |Oui  <br/> |Oui  <br/> (VBSS également disponible)  <br/> |Oui  <br/> |
|Messagerie instantanée et présence dans les fichiers Microsoft Word et Microsoft Excel (balises actives activées)  <br/> |Microsoft Word uniquement  <br/> |Microsoft Word uniquement  <br/> |Non  <br/> |
|Messagerie instantanée et présence sur les sites Microsoft SharePoint (Outlook doit être installé)  <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
   
& #x 2776 ; -Suppose que vous avez installé et qui sont en cours d’exécution sur le client Mac ou le Lync 2011 pour le client Mac un Skype pour les entreprises.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server et Skype pour les entreprises

Le tableau suivant décrit Skype pour la prise en charge de l’entreprise pour les différentes versions d’Exchange Server. Outlook doit être installé sur l’ordinateur client pour traiter les appels d’interface MAPI étendue et certaines fonctionnalités nécessitent l’utilisation d’Exchange Web Services (EWS).
  
**Skype pour les entreprises et la compatibilité d’Exchange Server**

|**Version d’Exchange Server**|**Skype pour la prise en charge de l’entreprise**|
|:-----|:-----|
|Exchange Server 2016  <br/> |Identique à la prise en charge d’Exchange Server 2013  <br/> |
|Exchange Server 2013  <br/> |Identique à la prise en charge de Microsoft Exchange Server 2010, avec l’ajout de  <br/>&bull;&nbsp;&nbsp;Magasin de contacts unifié  <br/>&bull;&nbsp;&nbsp;Photos haute résolution  <br/>&bull;&nbsp;&nbsp;Intégration d’archivage  <br/> **Remarque :** Pour plus d’informations, voir [Intégration de Skype pour Business Server 2015 avec Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/> |Les fonctionnalités suivantes sont disponibles uniquement par l’intermédiaire d’EWS :  <br/>&bull;&nbsp;&nbsp;Lire ou supprimer des éléments dans le dossier historique des conversations  <br/>&bull;&nbsp;&nbsp;Lire ou supprimer des messages vocaux  <br/>&bull;&nbsp;&nbsp;Afficher les informations de disponibilité étendues et objet de la réunion et l’emplacement  <br/>&bull;&nbsp;&nbsp;Synchronisation des contacts Exchange  <br/> Les dossiers publics sont une option dans Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>Voir aussi
 

[Configuration requise des clients Windows et prise en charge logicielle](windows-requirements.md)
  
[Planifier pour les clients de réunions (application Web et application de réunions)](meetings-clients.md)
#### 

[Interopérabilité des clients dans Lync 2013](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)
  
[Configuration requise du client](http://technet.microsoft.com/library/38f3a465-dac1-4381-bc59-270a4ef07ced.aspx)
  
[Exigences d’application Lync Windows Store](http://technet.microsoft.com/library/5f2e0a40-8450-4f61-b6f6-913fc1906020.aspx)

