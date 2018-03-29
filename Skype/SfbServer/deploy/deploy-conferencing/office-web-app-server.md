---
title: Configuration de l’intégration au serveur Office Web Apps Server dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 'Résumé : Lisez cette rubrique pour savoir comment configurer l’intégration entre Office Web Apps Server et Skype pour 2015 de serveur d’entreprise pour permettre des présentations PowerPoint pour les conférences web.'
ms.openlocfilehash: da6b5765cf62fc97fcc20b72e2411db306b37f0e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server-2015"></a>Configuration de l’intégration au serveur Office Web Apps Server dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour savoir comment configurer l’intégration entre Office Web Apps Server et Skype pour 2015 de serveur d’entreprise pour permettre des présentations PowerPoint pour les conférences web.
  
Skype pour Business Server utilise Office Web Apps Server pour gérer les présentations de PowerPoint pour les conférences web. Pour plus d’informations sur les avantages de cette approche, reportez-vous à la section [planifier la conférence dans Skype pour Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md).
  
Avant de pouvoir configurer Skype pour utiliser Office Web Apps Server Business Server, vous devez vous assurer que Office Web Apps Server est déjà déployée et configurée. Pour plus d’informations sur le serveur d’applications Web Office, consultez l’article [de déployer l’infrastructure : Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525). 
  
Une fois Office Web Apps Server a été correctement installé et que votre batterie de serveurs Web correctement configuré, vous devez alors configurer Skype pour Business Server communiquer avec le nouveau serveur en ajoutant l’URL de découverte de serveur de Office Web Apps à votre Skype pour les entreprises Topologie du serveur. 
  
> [!NOTE]
> La dernière itération d’Office Web Apps Server nommée Office en ligne, qui est pris en charge par Skype pour Business Server 2015. Pour plus de détails, reportez-vous à la [documentation du serveur en ligne de Office](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx). 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Configurer Skype pour Business Server communiquer avec le serveur d’applications Web Office

Pour ajouter Office Web Apps Server à votre topologie, procédez comme suit :
  
1.  Ouvrez Skype pour le Générateur de topologies Business Server.
    
2. Dans la boîte de dialogue **Générateur de topologies**, sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.
    
3. Dans la boîte de dialogue **Enregistrer la topologie sous**, tapez le nom de votre document de topologie (par exemple, **PreWebAppsServerTopology**) dans la zone **Nom du fichier\**, puis cliquez sur **Enregistrer**. Vous pouvez par la suite extraire et republier cette topologie si vous rencontrez des problèmes avec votre nouvelle topologie.
    
4. Dans le Générateur de topologie, développez successivement **Skype Entreprise Server**, le nom de votre site, **Pools frontaux Entreprise Edition**, puis cliquez avec le bouton droit sur l’un de vos pools et cliquez sur **Modifier les propriétés**.
    
5. Dans la boîte de dialogue **Modifier les propriétés**, sous l’onglet **Général**, recherchez l’en-tête **Serveur Office Web Apps associé**, puis cliquez sur **Nouveau** (ou sélectionnez un serveur Office Web Apps Server existant dans la liste déroulante).
    
6. Dans la boîte de dialogue **Définir un nouveau serveur Office Web Apps**, tapez le nom de domaine complet de votre ordinateur Office Web Apps Server dans la zone **Nom de domaine complet du serveur Office Web Apps**. L’URL de découverte du serveur Office Web Apps Server est alors automatiquement entrée dans la zone **URL de découverte du serveur Office Web Apps**.
    
  - Si Office Web Apps serveur est installé sur site et dans la même zone de réseau que Skype pour Business Server puis l’option **Qu'office Web Apps Server est déployé dans un réseau externe (c'est-à-dire, périmètre Internet)** doit être désactivée.
    
  - Si le serveur Office Web Apps Server est déployé à l’extérieur de votre pare-feu interne, sélectionnez alors l’option **Le serveur Office Web Apps est déployé sur un réseau externe (périmètre/Internet)**.
    
7. Dans la boîte de dialogue **Définir un nouveau serveur Office Web Apps**, cliquez sur **OK**. Ensuite, cliquez sur **OK** dans la boîte de dialogue **Modifier les propriétés**. L’URL de découverte d’Office Online doit alors figurer parmi les associations du pool.
    
Vous devez répéter ce processus pour chaque pool à associer à votre serveur Office Web Apps Server.
  
Après avoir ajouté l’URL de découverte à la topologie, vous devez ensuite publier cette topologie mise à jour. Pour cela, dans le Générateur de topologie :
  
1. Cliquez sur **Action**, puis sur **Publier la topologie**.
    
2. Dans l’Assistant Publication de la topologie, dans la page **Publier la topologie**, cliquez sur **Suivant**.
    
3. Dans la page **Assistant Publication terminé**, cliquez sur **Terminer**.
    
4. Fermez le Générateur de topologie.
    
## <a name="configure-access-for-external-users"></a>Configuration de l’accès pour les utilisateurs externes

Si vous souhaitez que les utilisateurs externes (c'est-à-dire les utilisateurs ouvre une session à partir de l’extérieur du pare-feu de votre organisation) à avoir accès à des présentations PowerPoint de serveur Office Web Apps, puis vous devez utiliser Office Web Apps Server et un serveur proxy inverse. Vous devrez également créer et configurer une règle de publication de site web, qui permet aux utilisateurs de se connecter au serveur. 
  
## <a name="validate-the-configuration"></a>Validation de la configuration

Après que Office Web Apps serveur a été ajouté à la topologie, et cette topologie a été publiée, vous devez voir deux nouveaux événements de journal des événements dans le Skype Business Server journal des événements. D’abord, un événement LS Data MCU (ID d’événement 41034) devrait être ajouté, cet événement va signaler la découverte du serveur Office Web Apps :
  
 **Le serveur de conférence Web Office Web Apps Server est découvert, le contenu PowerPoint est activé.**
  
En plus de cela, un autre événement LS Data MCU devrait être affiché (ID d’événement 41032), retournant les URL du serveur Office Web Apps. Par exemple, vous devriez voir un message semblable à :
  
 **La découverte du serveur de conférence Web Office Web Apps Server a réussi.**
  
 **Page de présentateur interne de serveur d’applications Web Office : https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0 &amp;incorporer =**
  
 **Page de participant interne de serveur d’applications Web Office : https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0 &amp;incorporer = true&amp;=**
  
Si vous avez configuré l’accès pour les utilisateurs externes, vous recevrez également un message similaire à celui-ci :
  
 **Page externe présentateur de serveur d’applications Web Office : https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0 &amp;incorporer**
  
 **Page de participant interne de serveur d’applications Web Office : https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0 &amp;incorporer = true&amp;**
  
Si vous voyez un événement LS données MCU avec l’ID d’événement de 41033 qui signifie que la détection du serveur d’applications Web Office a échoué. Dans ce cas, Skype pour Business Server va essayer autant de fois que nécessaire pour identifier le serveur nouvellement configuré Office Web Apps. Si le processus de découverte échoue à plusieurs reprises vous devez supprimer Office Web Apps Server à partir de votre document de topologie, publier la topologie mis à jour et réessayez d’ajouter Office Web Apps Server à la topologie, une fois résolus les problèmes de connectivité.
  
Si Office Web Apps Server semble être configurée correctement et qu’il a été reconnu par le processus de découverte, vous pouvez vérifier que Office Web Apps Server fonctionne comme prévu en partageant une présentation PowerPoint entre une paire de Skype pour les clients de l’entreprise. Si l’utilisateur A peut charger et afficher la présentation PowerPoint et si l’utilisateur B peut joindre la réunion, puis consultez cette présentation Office Web Apps Server fonctionne.
  
Même si Office Web Apps Server semble être configurée correctement, vous risque de recevoir le message d’erreur « certaines fonctionnalités de partage ne sont pas disponibles en raison de problèmes de connectivité de serveur » lorsque vous essayez de partager une présentation PowerPoint. Si vous recevez ce message d’erreur, vous devez redémarrer le Front-End (ou les serveurs) associé au nouveau serveur Office Web Apps.
  

