---
title: Gérer le 9-1-1 amélioré et le service Emplacement
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Skype Entreprise Server prend en charge les appels améliorés 9-1-1 (E9-1-1) à partir de clients Skype Entreprise. Lorsque vous configurez Skype Entreprise Server pour E9-1-1, les appels d’urgence passés à partir de Skype Entreprise incluent des informations d’emplacement de réponse d’urgence (ERL) provenant de la base de données du service Informations sur l’emplacement.
ms.openlocfilehash: 5b002e4043cb400b5f22a4b11bc70941a88abc2a
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676006"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a>Gérer le service 9-1-1 amélioré et le service Emplacement dans Skype pour Busines Server

Skype Entreprise Server prend en charge les appels améliorés 9-1-1 (E9-1-1) à partir de clients Skype Entreprise. Lorsque vous configurez Skype Entreprise Server pour E9-1-1, les appels d’urgence passés à partir de Skype Entreprise incluent des informations d’emplacement de réponse d’urgence (ERL) provenant de la base de données du service Informations sur l’emplacement. Utilisez les procédures décrites dans cet article pour gérer la stratégie d’emplacement.

> [!Note]
> Pour plus d’informations sur le déploiement de fonctionnalités de Voix Entreprise avancées, telles que E9-1-1 et le service Informations sur l’emplacement, consultez [Déployer des fonctionnalités avancées Voix Entreprise](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md).

Dans Skype Entreprise Server, vous pouvez utiliser la stratégie d’emplacement pour appliquer des paramètres liés à la fonctionnalité Améliorée 9-1-1 (E9-1-1) et aux paramètres d’emplacement pour les utilisateurs ou les contacts. La stratégie d’emplacement détermine si un utilisateur peut avoir recours au système E9-1-1 et, le cas échéant, le comportement d’un appel d’urgence. Par exemple, la stratégie d’emplacement permet de définir le numéro d’appel d’urgence (par exemple 911 aux États-Unis, 15 en France), de déterminer si le service de sécurité de l’entreprise doit être automatiquement averti et comment l’appel doit être acheminé.

Vous pouvez configurer des stratégies d’emplacement à partir du groupe **Configuration réseau** dans le Skype Entreprise Server Panneau de configuration. À partir de la Skype Entreprise Server Panneau de configuration vous pouvez afficher, créer, modifier ou supprimer des stratégies d’emplacement. Utilisez les procédures suivantes pour afficher des informations sur les stratégies d’emplacement. 


## <a name="view-location-policy-information"></a>Afficher les informations de stratégie d’emplacement 

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL Administration pour ouvrir le Skype Entreprise Server Panneau de configuration. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie d’emplacement**.

4.  Dans la page **Stratégie d’emplacement**, sélectionnez la stratégie d’emplacement que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.
 
    > [!NOTE]  
    > Vous ne pouvez afficher des informations que sur une seule stratégie d’emplacement à la fois.

Une stratégie unique, appelée Globale, existe par défaut. Il n’est pas possible de supprimer ou de renommer cette stratégie. Vous pouvez cependant la modifier. Cette stratégie s’applique à tous les utilisateurs et contacts, sauf si vous créez des stratégies de site ou par utilisateur. Les stratégies par utilisateur doivent être appliquées à des utilisateurs spécifiques.


## <a name="create-or-modify-a-location-policy"></a>Créer ou modifier une stratégie d’emplacement 

Dans Skype Entreprise Server, vous pouvez remplacer la durée par défaut entre les demandes du client pour une mise à jour d’emplacement à partir du service Informations d’emplacement. La valeur par défaut est 4 heures. Utilisez l’applet de commande **Set-CsLocationPolicy** avec le paramètre LocationRefreshInterval pour remplacer la valeur par défaut.


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a>Pour créer une stratégie d’emplacement dans le Skype Entreprise Server Panneau de configuration

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL Administration pour ouvrir le Skype Entreprise Server Panneau de configuration. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie d’emplacement**.

4.  Dans la page **Stratégie d’emplacement**, cliquez sur **Nouveau**, puis sélectionnez le type de stratégie que vous souhaitez créer :
    
      - Pour créer une stratégie de site, cliquez sur **Stratégie du site**. Dans **Sélectionner un site**, choisissez le site auquel vous souhaitez appliquer la stratégie et cliquez sur **OK**. Dans la page **Créer une stratégie d’emplacement**, le champ **Étendue** contient la valeur **Site** et le champ **Nom** contient le nom du site que vous avez choisi. Vous ne pouvez modifier aucun de ces champs. Une stratégie de site est automatiquement appliquée à tous les utilisateurs sur le site spécifié et remplace la stratégie globale qui leur était appliquée.
    
      - Pour créer une **stratégie de l’utilisateur**, cliquez sur **Stratégie de l’utilisateur**. Dans la page **Créer une stratégie d’emplacement**, le champ **Étendue** contient la valeur **Utilisateur**. Vous ne pouvez pas modifier cette valeur. Dans le champ **Nom**, tapez le nom que vous souhaitez donner à cette stratégie. Une stratégie de l’utilisateur ne s’applique pas automatiquement aux utilisateurs. Après avoir créé la stratégie de l’utilisateur, vous devez manuellement octroyer la stratégie aux utilisateurs ou aux sites réseau auxquels vous souhaitez que la stratégie s’applique.

5.  Renseignez les champs restants, comme suit :
    
      - **Activer les services d’urgence améliorés**   Activez cette case à cocher pour activer les utilisateurs associés à cette stratégie pour E9-1-1. Lorsque les services d’urgence sont activés, Skype Entreprise Server clients récupèrent les informations d’emplacement sur l’inscription et incluent ces informations lorsqu’un appel d’urgence est effectué.
    
      - **Emplacement**   Spécifiez l’une des valeurs suivantes :
        
          - **Requis**   L’utilisateur est invité à fournir des informations sur l’emplacement lorsque le client s’inscrit à un nouvel emplacement. L’utilisateur peut ignorer l’invite sans fournir aucune information. S’il fournit des informations, le fournisseur de services d’urgence répond d’abord à l’appel d’urgence pour vérifier l’emplacement, puis l’appel est transmis à l’opérateur du centre d’appels de la sécurité publique (c’est-à-dire l’opérateur des services d’urgence).
        
          - **Non requis**   L’utilisateur n’est pas invité à saisir un emplacement. Lorsqu’un appel est effectué sans informations d’emplacement, le fournisseur de services d’urgence y répond et demande qu’un emplacement lui soit indiqué.
        
          - **Avertissement**   Cette option est identique à **Obligatoire** , sauf que l’utilisateur ne peut pas ignorer l’invite sans entrer d’informations d’emplacement. L’utilisateur peut toujours appeler les services d’urgence, mais aucun autre appel ne peut être passé sans fournir les informations. De plus, un texte d’exclusion s’affiche pour informer l’utilisateur des conséquences du refus de fournir des informations sur l’emplacement. Pour définir le texte d’exclusion de responsabilité, vous devez utiliser le Skype Entreprise Server Management Shell pour exécuter l’applet **de commande Set-CsLocationPolicy** ou l’applet de commande **New-CsLocationPolicy** avec le paramètre EnhancedEmergencyServiceDisclaimer. Pour plus d’informations, consultez [Set-CsLocationPolicy](/powershell/module/skype/Set-CsLocationPolicy) ou [New-CsLocationPolicy](/powershell/module/skype/New-CsLocationPolicy).
          
    
      - **Utilisez l’emplacement pour les services d’urgence uniquement** Skype Entreprise pouvez utiliser les informations d’emplacement pour différentes raisons (par exemple, pour informer vos collègues de votre emplacement actuel). Activez cette case à cocher pour que les informations sur l’emplacement soient uniquement disponibles lors d’un appel d’urgence.
    
      - **Utilisation PSTN**   Réseau téléphonique commuté public qui permettra de déterminer l’itinéraire des communications vocales afin de router les appels d’urgence des clients à l’aide de ce profil. L’itinéraire associé à cette utilisation doit pointer sur une jonction SIP dédiée aux appels d’urgence ou à une passerelle ELIN (Emergency Location Identification Number) qui route les appels d’urgence vers le centre téléphonique de sécurité publique (Public Safety Answering Point ou PSAP) le plus proche.
    
      - **Numéro d’urgence**   Numéro qui est composé pour joindre les services d’urgence. Aux États-Unis il s’agit du 911. La chaîne doit être composée des chiffres 0 à 9 et peut avoir une longueur comprise entre 1 et 10 chiffres.
    
      - **Masque de numéro d’urgence**   Numéro que vous voulez traduire en valeur de numéro d’urgence lorsqu’il est composé. Par exemple, si vous entrez 212 dans ce champ et si la valeur du champ Numéro d’urgence est 911, le numéro appelé sera le 911 si un utilisateur compose le 212. Cela permet de composer d’autres numéros d’urgence et de pouvoir joindre quand même les services d’urgence (par exemple, si une personne provenant d’un pays où le numéro d’urgence est différent tente de composer ce numéro au lieu du numéro du pays dans lequel elle se trouve actuellement). Vous pouvez définir plusieurs masques d’appel d’urgence en séparant les valeurs par des points-virgules. Par exemple, 212;414. La longueur maximale de la chaîne est 100 caractères. Chaque caractère doit être un chiffre compris entre 0 et 9.
      

        > [!IMPORTANT]  
        > Assurez-vous que la valeur du masque d’appel n’est pas identique à un numéro figurant dans une plage de numéros d’appels parqués. Le routage du parcage d’appels aura priorité sur la conversion des chaînes d’appel d’urgence. Pour afficher les plages de numéros d’appels parqués, cliquez sur **Fonctionnalités vocales** dans la barre de navigation de gauche, puis cliquez sur **Parcage d’appel**. 

    
      - **URI de notification**   Un ou plusieurs URI (Uniform Resource Identifier) SIP à notifier lorsqu’un appel d’urgence est passé. Par exemple, le service de sécurité de l’entreprise peut être notifié par un message instantané pour chaque appel d’urgence. Si l’emplacement de l’appelant est disponible, cet emplacement sera inclus dans la notification. Plusieurs URI SIP peuvent être insérés dans une liste dans laquelle ils sont séparés par des virgules. Par exemple, « sip:security@litwareinc.com »,« sip:kmyer@litwareinc.com ». Les listes de distribution sont prises en charge. La chaîne doit comporter entre 1 et 256 caractères et commencer par le préfixe « sip: ». Avant que vous ne cliquiez dans le champ URI de notification un exemple est affiché.
    
      - **URI de la conférence**   URI SIP, dans ce cas le numéro de téléphone d’une tierce personne qui sera invitée à participer aux appels d’urgence. Par exemple, le service de sécurité de l’entreprise peut recevoir un appel l’invitant à écouter ou à participer à un appel d’urgence (en fonction de la valeur fournie dans le champ **Mode conférence**). La chaîne doit comporter entre 1 et 256 caractères et commencer par le préfixe sip:. Un exemple est affiché avant que vous ne cliquiez dans ce champ.
    
      - **Mode conférence**   Si vous spécifiez une valeur dans le champ **URI de la conférence**, le **mode conférence** détermine si une tierce personne peut participer à l’appel d’urgence ou seulement l’écouter. Spécifiez une des options suivantes :
        
          - **Unidirectionnel**   La personne tierce peut uniquement écouter la conversation entre l’appelant et l’opérateur du centre d’appels de la sécurité publique.
        
          - **Bidirectionnel**   Une tierce personne peut écouter et participer à l’appel entre l’appelant et l’opérateur du centre d’appels de la sécurité publique.

6.  Cliquez sur **Valider**.


    > [!IMPORTANT]  
    > Lorsque vous créez une stratégie utilisateur, cette stratégie ne s’applique initialement à aucun utilisateur ou site réseau. Pour appliquer la stratégie à un utilisateur, cliquez sur **Utilisateurs** dans la barre de navigation de gauche. Recherchez l’utilisateur auquel vous souhaitez appliquer la stratégie. Dans le menu **Edition**, cliquez sur **Afficher les détails**. Dans la page **Modifier l’utilisateur du serveur** , sélectionnez la nouvelle stratégie d’emplacement dans la liste déroulante **Stratégie d’emplacement** , puis cliquez sur **Valider**.<BR>Pour appliquer la stratégie à un site réseau, cliquez sur **Configuration réseau** dans la barre de navigation de gauche et cliquez sur **Site**. Recherchez le site réseau auquel vous souhaitez appliquer la stratégie. Dans le menu **Edition**, cliquez sur **Afficher les détails**. Dans **Modifier le site**, sélectionnez la nouvelle stratégie d’emplacement dans la liste déroulante **Stratégie d’emplacement**, puis cliquez sur **Valider**.


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a>Pour modifier une stratégie d’emplacement dans le Skype Entreprise Server Panneau de configuration

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL Administration pour ouvrir le Skype Entreprise Server Panneau de configuration. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie d’emplacement**.

4.  Dans la page **Stratégie d’emplacement**, sélectionnez la stratégie d’emplacement que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier la stratégie d’emplacement**, modifiez les champs comme il convient (pour plus d’informations, voir l’étape 5 dans la procédure de création d’une stratégie d’emplacement plus haut dans cette rubrique).

7.  Cliquez sur **Valider**.

        
## <a name="delete-a-location-policy"></a>Supprimer une stratégie d’emplacement


1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL Administration pour ouvrir le Skype Entreprise Server Panneau de configuration. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie d’emplacement**.

4.  Dans la page **Stratégie d’emplacement**, sélectionnez la stratégie d’emplacement que vous souhaitez supprimer.
   
    > [!NOTE]  
    > Vous pouvez supprimer plusieurs stratégies d’emplacement à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs stratégies. Ou, pour sélectionner toutes les stratégies, cliquez sur **Sélectionner tout** dans le menu **Edition**.


5.  Dans le menu **Edition**, cliquez sur **Supprimer**.

6.  Cliquez sur **OK**.

    > [!IMPORTANT]  
    > Vous ne pouvez pas supprimer la stratégie d’emplacement globale. Si vous tentez de supprimer cette stratégie vous obtiendrez un message d’erreur et les valeurs par défaut de cette stratégie seront rétablies.


## <a name="see-also"></a>Voir aussi

[Créer ou modifier des sites réseau](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[New-CsLocationPolicy](/powershell/module/skype/New-CsLocationPolicy)  

[Set-CsLocationPolicy](/powershell/module/skype/Set-CsLocationPolicy) 
 
[Remove-CsLocationPolicy](/powershell/module/skype/Remove-CsLocationPolicy)  

[Get-CsLocationPolicy](/powershell/module/skype/Get-CsLocationPolicy)