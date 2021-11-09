---
title: Configurer l’intégration avec Office Web Apps Server dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 'Résumé : Lisez cette rubrique pour découvrir comment configurer l’intégration entre Office Web Apps Server et Skype Entreprise Server pour activer les présentations PowerPoint pour les conférences web.'
ms.openlocfilehash: 291e246651a5c4f909f2e739e76de65d8c983c5b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835952"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>Configurer l’intégration avec Office Web Apps Server dans Skype Entreprise Server
 
**Résumé :** Lisez cette rubrique pour découvrir comment configurer l’intégration entre Office Web Apps Server et Skype Entreprise Server pour activer les présentations PowerPoint conférence web.
  
Skype Entreprise Server utilise Office Web Apps Server pour gérer PowerPoint présentations pour les conférences web. Pour plus d’informations sur les avantages de cette approche, voir [Plan for conferencing in Skype Entreprise Server](../../plan-your-deployment/conferencing/conferencing.md).
  
Avant de configurer Skype Entreprise Server pour utiliser Office Web Apps Server, vous devez vous assurer que Office Web Apps Server est déjà déployé et configuré. Pour plus d’informations Office Web Apps Server, voir l’article [Déployer l’infrastructure : Office Online Server](/webappsserver/deploy-the-infrastructure-office-web-apps-server). 
  
Une fois Office Web Apps Server correctement installé et votre batterie de serveurs Web correctement configurée, vous devez configurer Skype Entreprise Server pour communiquer avec le nouveau serveur en ajoutant l’URL de découverte Office Web Apps Server à votre topologie Skype Entreprise Server. 
  
> [!NOTE]
> La dernière itération de Office Web Apps Server est nommée Office Online Server, qui est prise en charge par Skype Entreprise Server. Pour plus d’informations, reportez-vous [à la documentation Office Online Server.](/officeonlineserver/office-online-server) 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Configurer Skype Entreprise Server pour communiquer avec Office Web Apps Server

Pour ajouter Office Web Apps Server à votre topologie, complétez les étapes suivantes :
  
1. Ouvrez Skype Entreprise Server générateur de topologie.
    
2. Dans la boîte de dialogue **Générateur de topologie**, sélectionnez **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.
    
3. Dans la boîte de dialogue **Enregistrer la topologie sous**, tapez le nom de votre document de topologie (par exemple, **PreWebAppsServerTopology**) dans la zone **Nom du fichier**, puis cliquez sur **Enregistrer**. Vous pouvez par la suite récupérer et republier cette topologie si vous rencontrez des problèmes avec votre nouvelle topologie.
    
4. Dans le Générateur de topologie, développez **Skype Entreprise Server,** développez le nom de votre site, **développez Êdition Entreprise pools** frontux, cliquez avec le bouton droit sur le nom de l’un de vos pools, puis cliquez sur **Modifier** les propriétés.
    
5. Dans la boîte de dialogue **Modifier les propriétés**, sous l’onglet **Général**, recherchez l’en-tête **Serveur Office Web Apps associé**, puis cliquez sur **Nouveau** (ou sélectionnez un serveur Office Web Apps Server existant dans la liste déroulante).
    
6. Dans la boîte de dialogue **Définir un nouveau serveur Office Web Apps**, tapez le nom de domaine complet de votre ordinateur Office Web Apps Server dans la zone **Nom de domaine complet du serveur Office Web Apps**. L’URL de découverte du serveur Office Web Apps Server est alors automatiquement entrée dans la zone **URL de découverte du serveur Office Web Apps**.
    
   - Si le serveur Office Web Apps Server est installé en local et dans la même zone réseau que Skype Entreprise Server, l’option Office Web Apps Server est déployée sur un réseau externe **(périmètre/Internet)** ne doit pas être sélectionnée.
    
   - Si le serveur Office Web Apps Server est déployé à l’extérieur de votre pare-feu interne, sélectionnez alors l’option **Le serveur Office Web Apps est déployé sur un réseau externe (périmètre/Internet)**.
    
7. Dans la **boîte de dialogue Définir un Office Web Apps Server,** cliquez sur **OK,** puis sur **OK** dans la boîte de dialogue Modifier **les** propriétés. L’URL de découverte est alors répertoriée comme l’une des associations du pool.
    
Vous devez répéter ce processus pour chaque pool à associer à votre serveur Office Web Apps Server.
  
Une fois que vous avez ajouté l’URL de découverte à la topologie, vous devez ensuite publier la topologie mise à jour. Pour cela, dans le Générateur de topologie :
  
1. Cliquez sur **Action**, puis sur **Publier la topologie**.
    
2. Dans l’Assistant Publication de la topologie, dans la page **Publier la topologie**, cliquez sur **Suivant**.
    
3. Dans la page **Assistant Publication terminé**, cliquez sur **Terminer**.
    
4. Fermez le Générateur de topologie.
    
## <a name="configure-access-for-external-users"></a>Configurer l’accès pour les utilisateurs externes

Si vous souhaitez que les utilisateurs externes (c’est-à-dire, les utilisateurs qui se connectent depuis l’extérieur du pare-feu de votre organisation) ont accès aux présentations Office Web Apps Server PowerPoint, vous devrez utiliser Office Web Apps Server et un serveur proxy inverse. Vous devez également créer et configurer une règle de publication de site web, ce qui permet de s’assurer que les utilisateurs sont en mesure de se connecter au serveur. 
  
## <a name="validate-the-configuration"></a>Valider la configuration

Une fois Office Web Apps Server a été ajouté à la topologie et une fois cette topologie publiée, vous devez voir deux nouveaux événements de journal des événements dans le journal des événements Skype Entreprise Server. Tout d’abord, un événement LS Data MCU (ID d’événement 41034) doit être ajouté ; Cet événement signale que l’Office Web Apps Server a été découvert :
  
 **Le serveur de conférence web Office Web Apps Server est découvert, PowerPoint contenu est activé.**
  
En plus de cela, un autre événement LS Data MCU devrait être affiché (ID d’événement 41032), retournant les URL du serveur Office Web Apps. Par exemple, vous devriez voir un message semblable à :
  
 **La découverte de Web Conferencing Server Office Web Apps Server a réussi.**
  
 **Office Page du présentateur interne Web Apps Server : https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ;embed=**
  
 **Office Page du participant interne Web Apps Server : https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp ;embed=true&amp;=**
  
Si vous avez configuré l’accès pour les utilisateurs externes, vous verrez également quelque chose de semblable à :
  
 **Office Page du présentateur externe Web Apps Server : https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ;embed**
  
 **Office Page du participant interne Web Apps Server : <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp> ;**
  
Si un événement LS Data MCU ayant l’ID d’événement 41033 s’affiche, cela signifie que la découverte d’Office Web Apps Server na pas fonctionné. Dans ce cas, Skype Entreprise Server essaiera autant de fois que nécessaire de découvrir le serveur Web Apps Server Office nouvellement configuré. Si le processus de découverte ne fonctionne pas à chaque essai, nous vous conseillons de supprimer Office Web Apps Server de votre document de topologie, de publier la topologie mise à niveau, puis d’essayer de rajouter Office Web Apps Server à votre topologie une fois les problèmes de topologie résolus.
  
Si Office Web Apps Server semble configuré correctement et a été reconnu par le processus de découverte, vous pouvez vérifier que Office Web Apps Server fonctionne comme prévu en partageant une présentation PowerPoint entre deux clients Skype Entreprise. Si l’utilisateur A peut charger et afficher la présentation PowerPoint et si l’utilisateur B peut ensuite rejoindre la réunion et consulter la présentation, alors Office Web Apps Server fonctionne correctement.
  
Même si Office Web Apps Server semble configuré correctement, vous pouvez potentiellement recevoir le message d’erreur « Certaines fonctionnalités de partage ne sont pas disponibles en raison de problèmes de connectivité du serveur » lorsque vous essayez de partager une présentation PowerPoint. Si vous recevez ce message d’erreur, vous devez redémarrer le ou les serveurs frontaux associés à la nouvelle configuration d’Office Web Apps Server.
