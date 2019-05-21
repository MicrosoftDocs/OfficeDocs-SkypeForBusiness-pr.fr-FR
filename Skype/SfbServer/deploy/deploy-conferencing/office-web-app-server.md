---
title: Configurer l’intégration avec Office Web Apps Server dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 'Résumé: pour plus d’informations sur la configuration de l’intégration entre Office Web Apps Server et Skype entreprise Server, voir présentation PowerPoint pour les conférences Web.'
ms.openlocfilehash: e657820a7a44197a344f23a67fdcd42ce0e593a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289110"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>Configurer l’intégration avec Office Web Apps Server dans Skype entreprise Server
 
**Résumé:** Pour plus d’informations sur la configuration de l’intégration d’Office Web Apps Server et de Skype entreprise Server à des présentations PowerPoint pour les conférences Web, consultez cette rubrique.
  
Skype entreprise Server utilise Office Web Apps Server pour gérer les présentations PowerPoint pour les conférences Web. Pour plus d’informations sur les avantages de cette approche, voir [planifier des conférences dans Skype entreprise Server](../../plan-your-deployment/conferencing/conferencing.md).
  
Pour pouvoir configurer Skype entreprise Server de manière à utiliser Office Web Apps Server, vous devez vous assurer qu’Office Web Apps Server est déjà déployé et configuré. Pour plus d’informations sur Office Web Apps Server, voir l’article [déploiement de l’infrastructure: Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525). 
  
Après l’installation d’Office Web Apps Server et la configuration correcte de votre batterie de serveurs Web, vous devez configurer Skype entreprise Server pour communiquer avec le nouveau serveur en ajoutant l’URL de découverte d’Office Web Apps Server à votre Skype entreprise. Topologie du serveur. 
  
> [!NOTE]
> La dernière itération d’Office Web Apps Server s’appelle Office Online Server, qui est prise en charge par Skype entreprise Server. Pour plus d’informations, reportez-vous à la [documentation du serveur Office Online](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx). 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Configurer Skype entreprise Server pour communiquer avec Office Web Apps Server

Pour ajouter Office Web Apps Server à votre topologie, procédez comme suit :
  
1. Ouvrez le générateur de topologie Skype entreprise Server.
    
2. Dans la boîte de dialogue **Générateur de topologies**, sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.
    
3. Dans la boîte de dialogue **Enregistrer la topologie sous**, tapez le nom de votre document de topologie (par exemple, **PreWebAppsServerTopology**) dans la zone **Nom du fichier\**, puis cliquez sur **Enregistrer**. Vous pouvez par la suite extraire et republier cette topologie si vous rencontrez des problèmes avec votre nouvelle topologie.
    
4. Dans le Générateur de topologie, développez successivement **Skype Entreprise Server**, le nom de votre site, **Pools frontaux Entreprise Edition**, puis cliquez avec le bouton droit sur l’un de vos pools et cliquez sur **Modifier les propriétés**.
    
5. Dans la boîte de dialogue **Modifier les propriétés**, sous l’onglet **Général**, recherchez l’en-tête **Serveur Office Web Apps associé**, puis cliquez sur **Nouveau** (ou sélectionnez un serveur Office Web Apps Server existant dans la liste déroulante).
    
6. Dans la boîte de dialogue **Définir un nouveau serveur Office Web Apps**, tapez le nom de domaine complet de votre ordinateur Office Web Apps Server dans la zone **Nom de domaine complet du serveur Office Web Apps**. L’URL de découverte du serveur Office Web Apps Server est alors automatiquement entrée dans la zone **URL de découverte du serveur Office Web Apps**.
    
   - Si Office Web Apps Server est installé en local et dans la même zone réseau que Skype entreprise Server, l’option **Office Web Apps Server déployée sur un réseau externe (c’est-à-dire le périmètre/Internet)** ne doit pas être sélectionnée.
    
   - Si le serveur Office Web Apps Server est déployé à l’extérieur de votre pare-feu interne, sélectionnez alors l’option **Le serveur Office Web Apps est déployé sur un réseau externe (périmètre/Internet)**.
    
7. Dans la boîte de dialogue **Définir un nouveau serveur Office Web Apps**, cliquez sur **OK**. Ensuite, cliquez sur **OK** dans la boîte de dialogue **Modifier les propriétés**. L’URL de découverte d’Office Online doit alors figurer parmi les associations du pool.
    
Vous devez répéter ce processus pour chaque pool à associer à votre serveur Office Web Apps Server.
  
Après avoir ajouté l’URL de découverte à la topologie, vous devez ensuite publier cette topologie mise à jour. Pour cela, dans le Générateur de topologie :
  
1. Cliquez sur **Action**, puis sur **Publier la topologie**.
    
2. Dans l’Assistant Publication de la topologie, dans la page **Publier la topologie**, cliquez sur **Suivant**.
    
3. Dans la page **Assistant Publication terminé**, cliquez sur **Terminer**.
    
4. Fermez le Générateur de topologie.
    
## <a name="configure-access-for-external-users"></a>Configuration de l’accès pour les utilisateurs externes

Si vous souhaitez que les utilisateurs externes (c’est-à-dire, les utilisateurs qui se connectent à partir de l’extérieur du pare-feu de votre organisation) puissent accéder aux présentations PowerPoint sur Office Web Apps Server, vous devez utiliser Office Web Apps Server et un serveur proxy inverse. Vous devrez également créer et configurer une règle de publication de site web, qui permet aux utilisateurs de se connecter au serveur. 
  
## <a name="validate-the-configuration"></a>Validation de la configuration

Une fois qu’Office Web Apps Server a été ajouté à la topologie et après la publication de cette topologie, vous devriez voir deux nouveaux événements du journal des événements dans le journal des événements de Skype entreprise Server. D’abord, un événement LS Data MCU (ID d’événement 41034) devrait être ajouté, cet événement va signaler la découverte du serveur Office Web Apps :
  
 **Le serveur de conférence Web Office Web Apps Server est découvert, le contenu PowerPoint est activé.**
  
En plus de cela, un autre événement LS Data MCU devrait être affiché (ID d’événement 41032), retournant les URL du serveur Office Web Apps. Par exemple, vous devriez voir un message semblable à :
  
 **La découverte du serveur de conférence Web Office Web Apps Server a réussi.**
  
 **Page de présentateur interne d’Office Web Apps https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&ampServer:; embed =**
  
 **Page des participants internes d’Office Web Apps Server https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp:; incorporer = true&amp;=**
  
Si vous avez configuré l’accès pour les utilisateurs externes, vous verrez également un aspect semblable à ce qui suit:
  
 **Page de présentateur externe Office Web Apps Server https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp:; incorporer**
  
 **Page des participants au serveur Office Web Apps Server <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>:;**
  
Si vous voyez un événement MCU de données LS avec l’ID d’événement de 41033 qui signifie que la découverte d’Office Web Apps Server a échoué. Le cas échéant, Skype entreprise Server tente autant de fois que nécessaire pour découvrir le serveur Office Web Apps que vous venez de configurer. Si le processus de découverte échoue à plusieurs reprises, il est recommandé de supprimer Office Web Apps Server de votre document topologique, de publier la topologie mise à jour, puis de réessayer d’ajouter Office Web Apps Server à la topologie suite à la résolution des problèmes de connectivité.
  
Si Office Web Apps Server semble correctement configuré et a été reconnu par le processus de découverte, vous pouvez vérifier qu’Office Web Apps Server fonctionne comme prévu en partageant une présentation PowerPoint entre deux clients Skype entreprise. Si l’utilisateur A peut charger et afficher la présentation PowerPoint et s’il peut rejoindre la réunion et voir cette présentation, Office Web Apps Server fonctionne.
  
Même si Office Web Apps Server semble correctement configuré, vous pouvez recevoir le message d’erreur «certaines fonctionnalités de partage ne sont pas disponibles en raison de problèmes de connectivité du serveur» lorsque vous essayez de partager une présentation PowerPoint. Si vous recevez ce message d’erreur, vous devez redémarrer le ou les serveurs frontaux associés au nouveau serveur Office Web Apps.
  

