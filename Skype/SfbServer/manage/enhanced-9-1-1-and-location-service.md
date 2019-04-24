---
title: Gérer les enhanced 9-1-1 et le service d’emplacement
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype pour Business Server prend en charge Enhanced 9-1-1 (E9-1-1) l’appel de Skype pour les clients d’entreprise. Lorsque vous configurez Skype pour Business Server pour E9-1-1, les appels d’urgence émis à partir de Skype pour les entreprises contiennent des informations d’emplacement de réponse d’urgence (ERL) à partir de la base de données du service informations d’emplacement.
ms.openlocfilehash: 31e1d529c8fb60145bc1ab4a22a75660d9f3ef63
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200301"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a>Gérer les enhanced 9-1-1 et le service d’emplacement dans Skype pour serveur Busines

Skype pour Business Server prend en charge Enhanced 9-1-1 (E9-1-1) l’appel de Skype pour les clients d’entreprise. Lorsque vous configurez Skype pour Business Server pour E9-1-1, les appels d’urgence émis à partir de Skype pour les entreprises contiennent des informations d’emplacement de réponse d’urgence (ERL) à partir de la base de données du service informations d’emplacement. Utilisez les procédures dans cet article pour gérer la stratégie d’emplacement.

> [!Note]
> Pour plus d’informations sur le déploiement des fonctionnalités avancées de voix entreprise, telles que E9-1-1 et le service informations d’emplacement, voir [déploiement d’Enterprise Voice fonctionnalités avancées](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md).

Dans Skype pour Business Server, vous pouvez utiliser la stratégie d’emplacement pour appliquer les paramètres qui sont associées à la fonctionnalité Enhanced 9-1-1 (E9-1-1) et pour les paramètres d’emplacement pour les utilisateurs ou les contacts. La stratégie d’emplacement détermine si un utilisateur est activé pour E9-1-1 et si c’est le cas quel est le comportement d’un appel d’urgence. Par exemple, vous pouvez utiliser la stratégie d’emplacement pour définir le numéro constitue un appel d’urgence (911, par exemple, aux États-Unis), si sécurité de l’entreprise doit être notifiée automatiquement, et comment l’appel doit être routé.

Vous pouvez configurer des stratégies d’emplacement à partir du groupe **Configuration réseau** dans le Skype pour le panneau de configuration serveur Business. À partir de la Skype pour le panneau de configuration serveur Business, vous pouvez afficher, créer, modifier ou supprimer des stratégies d’emplacement. Utilisez la procédure suivante pour afficher des informations sur les stratégies d’emplacement. 


## <a name="view-location-policy-information"></a>Afficher les informations de stratégie emplacement 

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Stratégie d’emplacement**.

4.  Dans la page **Stratégie d’emplacement** , sélectionnez la stratégie d’emplacement que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.
 
    > [!NOTE]  
    > Vous ne pouvez afficher des informations sur la stratégie d’un emplacement à la fois.

Une stratégie unique, appelée Global, il existe par défaut et ne peuvent pas être supprimée ou renommée. Toutefois, vous pouvez modifier la stratégie globale. Cette stratégie s’applique à tous les utilisateurs et les contacts, sauf si vous créez des stratégies de site ou utilisateur. Stratégies par utilisateur doivent être appliquées à des utilisateurs spécifiques.


## <a name="create-or-modify-a-location-policy"></a>Créer ou modifier une stratégie d’emplacement 

Dans Skype pour Business Server, vous pouvez substituer le délai entre les demandes des clients pour une mise à jour de l’emplacement du service informations d’emplacement par défaut. La valeur par défaut est de 4 heures. Utilisez l’applet de commande **Set-CsLocationPolicy** avec le paramètre LocationRefreshInterval pour remplacer la valeur par défaut.


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a>Pour créer une stratégie d’emplacement dans la Skype pour Business Server Control Panel

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Stratégie d’emplacement**.

4.  Dans la page **Stratégie d’emplacement** , cliquez sur **Nouveau** , puis sélectionnez le type de stratégie que vous souhaitez créer :
    
      - Pour créer une stratégie de site, cliquez sur **stratégie de Site**. Dans **Sélectionner un Site**, sélectionnez le site auquel vous souhaitez que la stratégie appliquée et cliquez sur **OK**. Dans la page **Stratégie d’emplacement** , le champ **étendue** contient la valeur **Site**et le champ **nom** contient le nom du site que vous avez choisi. Vous ne pouvez pas modifier un de ces champs. Une stratégie de site est automatiquement appliquée à tous les utilisateurs sur le site spécifié et remplace la stratégie globale pour les utilisateurs.
    
      - Pour créer une **stratégie utilisateur**, cliquez sur **stratégie de l’utilisateur**. Dans la **Nouvelle stratégie d’emplacement**, le champ **étendue** contient la valeur **utilisateur**. Vous ne pouvez pas modifier cette valeur. Dans le champ **nom** , tapez le nom à attribuer à cette stratégie. Une stratégie utilisateur ne s’applique pas automatiquement à tous les utilisateurs. Après avoir créé la stratégie utilisateur, vous devez accorder manuellement la stratégie pour les utilisateurs ou les sites de réseau auquel vous souhaitez stratégie à appliquer.

5.  Renseignez les champs restants, comme suit :
    
      - **Activer améliorée des services d’urgence**   Activez cette case à cocher pour activer les utilisateurs associés à cette stratégie pour E9-1-1. Lorsque les services d’urgence sont activés, Skype pour les clients Business Server système récupérer les informations d’emplacement de l’enregistrement et inclure ces informations lors d’un appel d’urgence.
    
      - **Emplacement**   spécifier une des valeurs suivantes :
        
          - **Requis**   invitera l’utilisateur à entrer des informations sur l’emplacement lorsque le client s’inscrit à un nouvel emplacement. L’utilisateur peut ignorer l’invite sans saisir aucune information. Si les informations entrées, un appel d’urgence est tout d’abord pris par le fournisseur de services d’urgence pour vérifier l’emplacement avant d’être acheminés vers l’opérateur Public Safety Answering Point (PSAP) (autrement dit, le 911 opérateur).
        
          - **Non requis**   l’utilisateur ne sera pas invité à entrer un emplacement. Lorsqu’un appel est effectué sans aucune information d’emplacement, le fournisseur de services d’urgence sont alors répondre à l’appel et demandez à un emplacement.
        
          - **Notification d’exclusion**   cette option est identique à **requis** , sauf que l’utilisateur ne peut pas ignorer l’invite sans saisir les informations d’emplacement. L’utilisateur a toujours peut effectuer un appel d’urgence, mais aucun autre appel ne peut être passé sans saisir les informations. En outre, texte d’exclusion s’affichera à l’utilisateur qui avertit les conséquences du refus de saisir des informations d’emplacement. Pour définir le texte d’exclusion, vous devez utiliser le Skype pour Business Server Management Shell pour exécuter l’applet de commande **Set-CsLocationPolicy** ou l’applet de commande **New-CsLocationPolicy** avec le paramètre EnhancedEmergencyServiceDisclaimer. Pour plus d’informations, voir [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) ou [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy).
          
    
      - **Utiliser l’emplacement pour les services d’urgence** Skype pour les entreprises permettre utiliser les informations d’emplacement pour différentes raisons (par exemple, pour informer des collègues à propos de votre emplacement actuel). Activez cette case à cocher pour vérifier les informations d’emplacement sont disponibles uniquement pour une utilisation avec un appel d’urgence.
    
      - **Utilisation PSTN**   commuté l’utilisation du réseau (RTC) téléphone qui sera utilisée pour déterminer quel itinéraire vocal sera utilisé pour acheminer les appels d’urgence de clients utilisant ce profil. L’itinéraire associé à cette utilisation doit pointer sur une jonction SIP dédiée aux appels d’urgence ou à une passerelle d’urgence ELIN Location Identification Number () qui achemine les appels d’urgence pour le plus proche Public Safety Answering pointez (PSAP).
    
      - **Numéro d’urgence**   le numéro qui est composé pour joindre les services d’urgence. Aux États-Unis, cette valeur est 911. La chaîne doit être composée des chiffres 0 à 9 et peut être de 1 à 10 chiffres.
    
      - **Masque de numérotation d’urgence**   un numéro que vous souhaitez traduire la valeur de la valeur numérique de numérotation d’urgence lorsqu’il est composé. Par exemple, si vous entrez une valeur de 212 dans ce champ et le champ de numéro de numérotation d’urgence a la valeur 911, si un utilisateur compose 212 l’appel sera (911). Ainsi, pour les numéros d’urgence substitution être composé tout en conservant l’appel joindre les services d’urgence (par exemple, si une personne de votre pays ou région avec un autre numéro d’urgence tente de numérotation que le pays ou la région s numérique plutôt que le numéro de la pays ou région dans que se trouvent actuellement). Vous pouvez définir plusieurs masques de numérotation d’urgence en séparant les valeurs par des points-virgules. Par exemple, 212 ; 414. Longueur maximale de la chaîne est de 100 caractères. Chaque caractère doit être un chiffre de 0 à 9.
      

        > [!IMPORTANT]  
        > Assurez-vous que la valeur de masque de numérotation spécifié n’est pas identique à un nombre dans une plage d’orbites de parcage d’appel. Routage des appels park ont priorité sur la conversion de chaînes de numérotation d’urgence. Pour visualiser les existants le plages d’orbites de parcage d’appel, cliquez sur **Fonctionnalités vocales** dans la barre de navigation de gauche, puis sur **Mise en garde d’appels**. 

    
      - **URI de notification**   un ou plusieurs SIP Uniform Resource Identifier (URI) pour être averti lorsqu’un appel d’urgence est effectué. Par exemple, le bureau de sécurité d’entreprise peut être informé via un message instantané chaque fois qu’un appel d’urgence est effectué. Si l’emplacement de l’appelant est disponible cet emplacement sera inclus dans la notification. Plusieurs URI SIP peuvent être inclus dans une liste séparée par des virgules. Par exemple, « sip:security@litwareinc.com », « sip:kmyer@litwareinc.com ». Listes de distribution sont prises en charge. La chaîne doit être comprise entre 1 et 256 caractères et doit commencer par le préfixe « sip : ». Avant de cliquer sur dans le champ URI de Notification un exemple s’affiche.
    
      - **URI de conférence**   l’URI SIP, dans ce cas, le numéro de téléphone d’un tiers qui sera invité à participer à tous les appels d’urgence effectués. Par exemple, le bureau de sécurité société peut recevoir un appel lors d’un appel d’urgence et écouter ou participer à cet appel (selon la valeur fournie dans le champ **mode conférence** ). La chaîne doit être comprise entre 1 et 256 caractères et doit commencer par le préfixe sip :. Un exemple est affiché jusqu'à ce que vous cliquez à l’intérieur de ce champ.
    
      - **Mode conférence**   si vous spécifiez une valeur dans le champ **URI de la conférence** , le **mode conférence** détermine si une tierce partie peut participer à l’appel ou peut uniquement écouter. Spécifiez une des options suivantes :
        
          - **One-Way**   un tiers peut uniquement écouter la conversation entre l’appelant et l’opérateur du centre.
        
          - **Bidirectionnelle**   un tiers peut écouter et participer à l’appel entre l’appelant et l’opérateur du centre.

6.  Cliquez sur **Valider**.


    > [!IMPORTANT]  
    > Lorsque vous créez une stratégie utilisateur, à l’origine cette stratégie ne s’applique pas à des utilisateurs ou des sites réseau. Pour appliquer la stratégie à un utilisateur, cliquez sur **utilisateurs** , dans la barre de navigation de gauche. Recherchez l’utilisateur auquel vous souhaitez appliquer la stratégie. Dans le menu **Edition**, cliquez sur **Afficher les détails**. Dans la page **Modifier l’utilisateur Server** , sélectionnez la nouvelle stratégie d’emplacement dans la liste déroulante **stratégie d’emplacement** , puis sur **Valider**.<BR>Pour appliquer la stratégie à un site réseau, cliquez sur **Configuration réseau** dans la barre de navigation de gauche, puis sur **sites**. Recherchez le site de réseau auquel vous souhaitez appliquer la stratégie. Dans le menu **Edition**, cliquez sur **Afficher les détails**. Dans **Modifier le Site**, sélectionnez la nouvelle stratégie d’emplacement dans la liste déroulante **stratégie d’emplacement** , puis sur **Valider**.


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a>Pour modifier une stratégie d’emplacement dans la Skype pour Business Server Control Panel

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Stratégie d’emplacement**.

4.  Dans la page **Stratégie d’emplacement** , sélectionnez la stratégie d’emplacement que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier la stratégie emplacement** , modifiez les champs comme il convient (pour plus d’informations, voir l’étape 5 dans la « pour créer une stratégie d’emplacement » plus haut dans cette rubrique).

7.  Cliquez sur **Valider**.

        
## <a name="delete-a-location-policy"></a>Supprimer une stratégie d’emplacement


1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Stratégie d’emplacement**.

4.  Dans la page **Stratégie d’emplacement** , sélectionnez la stratégie d’emplacement que vous souhaitez supprimer.
   
    > [!NOTE]  
    > Vous pouvez supprimer plusieurs stratégies d’emplacement à la fois. Pour ce faire, appuyez sur la touche CTRL ENFONCÉE et sélectionnez plusieurs stratégies de tout en maintenant la touche CTRL enfoncée. Ou, pour sélectionner toutes les stratégies, cliquez sur **Sélectionner tout** dans le menu **Edition** .


5.  Dans le menu **Edition** , cliquez sur **Supprimer**.

6.  Cliquez sur **OK**.

    > [!IMPORTANT]  
    > Vous ne pouvez pas supprimer la stratégie d’emplacement globale. Si vous tentez de supprimer la stratégie globale, vous recevrez un message d’avertissement et cette stratégie est réinitialisée à ses valeurs par défaut.


## <a name="see-also"></a>Voir aussi

[Créer ou modifier des sites réseau](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[Nouvelle-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  

[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 
 
[Remove-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  

[Get-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
