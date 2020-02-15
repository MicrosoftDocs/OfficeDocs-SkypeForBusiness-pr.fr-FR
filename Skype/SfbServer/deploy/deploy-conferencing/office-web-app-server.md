---
title: Configurer l’intégration à Office Web Apps Server dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 'Résumé : consultez cette rubrique pour découvrir comment configurer l’intégration entre Office Web Apps Server et Skype entreprise Server pour activer les présentations PowerPoint pour la conférence Web.'
ms.openlocfilehash: fee5939e8441457e3cee66e266baacd144ada288
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983919"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>Configurer l’intégration à Office Web Apps Server dans Skype entreprise Server
 
**Résumé :** Lisez cette rubrique pour découvrir comment configurer l’intégration entre Office Web Apps Server et Skype entreprise Server pour activer des présentations PowerPoint pour la conférence Web.
  
Skype entreprise Server utilise Office Web Apps Server pour gérer les présentations PowerPoint pour les conférences Web. Pour plus d’informations sur les avantages de cette approche, reportez-vous à la rubrique [plan for Conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md).
  
Avant de pouvoir configurer Skype entreprise Server pour l’utilisation d’Office Web Apps Server, vous devez vous assurer qu’Office Web Apps Server est déjà déployé et configuré. Pour plus d’informations sur Office Web Apps Server, consultez l’article [Deploy the infrastructure : Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525). 
  
Une fois l’installation d’Office Web Apps Server correctement effectuée et votre batterie de serveurs Web correctement configurée, vous devez configurer Skype entreprise Server pour qu’il communique avec le nouveau serveur en ajoutant l’URL de découverte d’Office Web Apps Server à Skype entreprise. Topologie de serveur. 
  
> [!NOTE]
> La dernière itération d’Office Web Apps Server est appelée Office Online Server, qui est pris en charge par Skype entreprise Server. Pour plus d’informations, reportez-vous à la [documentation d’Office Online Server](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx). 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Configurer Skype entreprise Server pour communiquer avec Office Web Apps Server

Pour ajouter le serveur Office Web Apps Server à votre topologie, procédez comme suit :
  
1. Ouvrez le générateur de topologie Skype entreprise Server.
    
2. Dans la boîte de dialogue **Générateur de topologie**, sélectionnez **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.
    
3. Dans la boîte de dialogue **Enregistrer la topologie sous**, tapez le nom de votre document de topologie (par exemple, **PreWebAppsServerTopology**) dans la zone **Nom du fichier**, puis cliquez sur **Enregistrer**. Vous pouvez par la suite récupérer et republier cette topologie si vous rencontrez des problèmes avec votre nouvelle topologie.
    
4. Dans le générateur de topologies, développez **Skype entreprise Server**, développez le nom de votre site, développez **Pools frontaux Enterprise Edition**, cliquez avec le bouton droit sur le nom de l’un de vos pools, puis cliquez sur **modifier les propriétés**.
    
5. Dans la boîte de dialogue **Modifier les propriétés**, sous l’onglet **Général**, recherchez l’en-tête **Serveur Office Web Apps associé**, puis cliquez sur **Nouveau** (ou sélectionnez un serveur Office Web Apps Server existant dans la liste déroulante).
    
6. Dans la boîte de dialogue **Définir un nouveau serveur Office Web Apps**, tapez le nom de domaine complet de votre ordinateur Office Web Apps Server dans la zone **Nom de domaine complet du serveur Office Web Apps**. L’URL de découverte du serveur Office Web Apps Server est alors automatiquement entrée dans la zone **URL de découverte du serveur Office Web Apps**.
    
   - Si Office Web Apps Server est installé sur site et dans la même zone de réseau que Skype entreprise Server, l’option le **serveur Office Web Apps est déployé sur un réseau externe (périmètre/Internet)** ne doit pas être sélectionné.
    
   - Si le serveur Office Web Apps Server est déployé à l’extérieur de votre pare-feu interne, sélectionnez alors l’option **Le serveur Office Web Apps est déployé sur un réseau externe (périmètre/Internet)**.
    
7. Dans la boîte de dialogue **définir un nouveau serveur Office Web Apps Server** , cliquez sur **OK**, puis sur **OK** dans la boîte de dialogue **modifier les propriétés** . L’URL de découverte est ensuite indiquée comme l’une des associations du pool.
    
Vous devez répéter ce processus pour chaque pool à associer à votre serveur Office Web Apps Server.
  
Une fois que vous avez ajouté l’URL de découverte à la topologie, vous devez publier la topologie mise à jour. Pour cela, dans le Générateur de topologie :
  
1. Cliquez sur **Action**, puis sur **Publier la topologie**.
    
2. Dans l’Assistant Publication de la topologie, dans la page **Publier la topologie**, cliquez sur **Suivant**.
    
3. Dans la page **Assistant Publication terminé**, cliquez sur **Terminer**.
    
4. Fermez le Générateur de topologie.
    
## <a name="configure-access-for-external-users"></a>Configurer l’accès pour les utilisateurs externes

Si vous souhaitez que des utilisateurs externes (c’est-à-dire, des utilisateurs qui se connectent en dehors du pare-feu de votre organisation) aient accès aux présentations Office Web Apps Server PowerPoint, vous devez utiliser Office Web Apps Server et un serveur proxy inverse. Vous devrez également créer et configurer une règle de publication de site Web, ce qui permet de s’assurer que les utilisateurs peuvent se connecter au serveur. 
  
## <a name="validate-the-configuration"></a>Validation de la configuration

Une fois qu’Office Web Apps Server a été ajouté à la topologie et une fois la topologie publiée, vous devez voir deux nouveaux événements de journal des événements dans le journal des événements de Skype entreprise Server. Tout d’abord, un événement de MCU de données LS (ID d’événement 41034) doit être ajouté ; Cet événement signale que le serveur Office Web Apps a été découvert :
  
 **Le serveur de conférence Web Office Web Apps Server est découvert, le contenu PowerPoint est activé.**
  
En plus de cela, un autre événement LS Data MCU devrait être affiché (ID d’événement 41032), retournant les URL du serveur Office Web Apps. Par exemple, vous devriez voir un message semblable à :
  
 **Serveur de conférence Web la découverte d’Office Web Apps Server a réussi.**
  
 **Page du présentateur interne Office Web Apps Server https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp:; embed =**
  
 **Page du participant interne Office Web Apps Server : https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp; embed = true&amp;=**
  
Si vous avez configuré l’accès pour les utilisateurs externes, vous verrez également un message semblable à celui-ci :
  
 **Page du présentateur externe Office Web Apps Server https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp:; embed**
  
 **Page du participant interne Office Web Apps Server : <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>;**
  
Si un événement LS Data MCU ayant l’ID d’événement 41033 s’affiche, cela signifie que la découverte d’Office Web Apps Server na pas fonctionné. Dans ce cas, Skype entreprise Server essaiera autant de fois que nécessaire pour découvrir le serveur Office Web Apps nouvellement configuré. Si le processus de découverte ne fonctionne pas à chaque essai, nous vous conseillons de supprimer Office Web Apps Server de votre document de topologie, de publier la topologie mise à niveau, puis d’essayer de rajouter Office Web Apps Server à votre topologie une fois les problèmes de topologie résolus.
  
Si Office Web Apps Server semble être configuré correctement et qu’il a été reconnu par le processus de découverte, vous pouvez vérifier qu’Office Web Apps Server fonctionne comme prévu en partageant une présentation PowerPoint entre deux clients Skype entreprise. Si l’utilisateur A peut charger et afficher la présentation PowerPoint et si l’utilisateur B peut ensuite rejoindre la réunion et consulter la présentation, alors Office Web Apps Server fonctionne correctement.
  
Même si Office Web Apps Server semble être correctement configuré, vous pouvez recevoir le message d’erreur « certaines fonctionnalités de partage ne sont pas disponibles en raison de problèmes de connectivité au serveur » lorsque vous essayez de partager une présentation PowerPoint. Si vous recevez ce message d’erreur, vous devez redémarrer le ou les serveurs frontaux associés à la nouvelle configuration d’Office Web Apps Server.
  

