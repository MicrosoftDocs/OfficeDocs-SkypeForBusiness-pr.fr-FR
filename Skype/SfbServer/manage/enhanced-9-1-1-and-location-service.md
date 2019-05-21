---
title: Gérer les 9-1-1 améliorés et le service de localisation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype entreprise Server prend en charge les appels 9-1-1 de meilleure qualité (E9-1-1) à partir des clients Skype entreprise. Lorsque vous configurez Skype entreprise Server pour E9-1-1, les appels d’urgence placés dans Skype entreprise incluent des informations de lieu de réponse d’urgence de la base de données de service des informations de géolocalisation.
ms.openlocfilehash: a0cf7254e12f00a01082b7aad71ce350cb382b9c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280298"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a>Gestion du 9-1-1 amélioré et du service de localisation dans Skype pour entreprise Server

Skype entreprise Server prend en charge les appels 9-1-1 de meilleure qualité (E9-1-1) à partir des clients Skype entreprise. Lorsque vous configurez Skype entreprise Server pour E9-1-1, les appels d’urgence placés dans Skype entreprise incluent des informations de lieu de réponse d’urgence de la base de données de service des informations de géolocalisation. Suivez les procédures décrites dans cet article pour gérer la stratégie d’emplacement.

> [!Note]
> Pour plus d’informations sur le déploiement de fonctionnalités avancées d’entreprise voix, telles que E9-1-1 et le service d’information d’emplacement, voir [déployer les fonctionnalités avancées d’Enterprise Voice](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md).

Dans Skype entreprise Server, vous pouvez utiliser la stratégie d’emplacement pour appliquer les paramètres relatifs à la fonctionnalité améliorée 9-1-1 (E9-1-1) et aux paramètres d’emplacement des utilisateurs ou des contacts. La stratégie d’emplacement détermine si un utilisateur est activé pour E9-1-1 et, si oui, le comportement d’un appel d’urgence. Par exemple, vous pouvez utiliser la stratégie d’emplacement pour définir le numéro constituant un appel d’urgence (par exemple, 911 aux États-Unis), si la sécurité d’entreprise doit être automatiquement notifiée et la manière dont l’appel doit être routé.

Vous pouvez configurer des stratégies d’emplacement à partir du groupe de **Configuration réseau** dans le panneau de configuration Skype entreprise Server. Le panneau de configuration Skype entreprise Server vous permet d’afficher, de créer, de modifier ou de supprimer des stratégies d’emplacement. Pour afficher des informations sur les stratégies d’emplacement, procédez comme suit. 


## <a name="view-location-policy-information"></a>Afficher les informations de stratégie d’emplacement 

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **stratégie d’emplacement**.

4.  Dans la page de **stratégie d’emplacement** , sélectionnez la stratégie d’emplacement que vous voulez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.
 
    > [!NOTE]  
    > Vous pouvez uniquement afficher des informations sur une stratégie d’emplacement à la fois.

Une stratégie unique, appelée global, existe par défaut et ne peut pas être supprimée ou renommée. Toutefois, vous pouvez modifier la stratégie globale. Ce paramètre s’applique à tous les utilisateurs et contacts, sauf si vous créez des stratégies de site ou des stratégies par utilisateur. Les stratégies par utilisateur doivent être appliquées à des utilisateurs spécifiques.


## <a name="create-or-modify-a-location-policy"></a>Créer ou modifier une stratégie d’emplacement 

Dans Skype entreprise Server, vous pouvez remplacer la durée par défaut entre les demandes de client pour une mise à jour d’emplacement du service d’informations d’emplacement. La valeur par défaut est 4 heures. Utilisez l’applet de cmdlet **Set-CsLocationPolicy** avec le paramètre LocationRefreshInterval pour remplacer la valeur par défaut.


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a>Pour créer une nouvelle stratégie d’emplacement dans le panneau de configuration Skype entreprise Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **stratégie d’emplacement**.

4.  Dans la page de **stratégie d’emplacement** , cliquez sur **nouveau** , puis sélectionnez le type de stratégie que vous voulez créer:
    
      - Pour créer une stratégie de site, cliquez sur **stratégie de site**. Dans **Sélectionner un site**, sélectionnez le site auquel vous voulez appliquer la stratégie, puis cliquez sur **OK**. Dans la page **nouvelle stratégie d’emplacement** , le champ **étendue** contient la valeur **site**et le champ **nom** contient le nom du site que vous avez choisi. Vous ne pouvez pas modifier l’un de ces champs. Une stratégie de site est appliquée automatiquement à tous les utilisateurs du site spécifié et remplace la politique globale de ces utilisateurs.
    
      - Pour créer une **stratégie d’utilisateur**, cliquez sur stratégie de l' **utilisateur**. Dans la **nouvelle stratégie d’emplacement**, le champ **étendue** contient la valeur **utilisateur**. Vous ne pouvez pas modifier cette valeur. Dans le champ **nom** , entrez le nom que vous souhaitez attribuer à cette stratégie. Une stratégie d’utilisateur ne s’applique pas automatiquement à tous les utilisateurs. Après la création de la stratégie de l’utilisateur, vous devez l’octroyer manuellement aux utilisateurs ou aux sites du réseau auxquels vous voulez appliquer la stratégie.

5.  Complétez les champs restants comme suit:
    
      - **Activer les services**   d’urgence améliorés activez cette case à cocher pour autoriser les utilisateurs associés à cette stratégie pour E9-1-1. Lorsque les services d’urgence sont activés, les clients Skype entreprise Server récupèrent les informations d’emplacement sur l’inscription et incluent ces informations lors de l’appel d’urgence.
    
      - **Emplacement**   spécifiez l’une des valeurs suivantes:
        
          - **Requis**   l’utilisateur est invité à entrer les informations d’emplacement lorsque le client s’inscrit à un nouvel emplacement. L’utilisateur peut ignorer l’invite sans entrer d’information. Si les informations sont entrées, un appel d’urgence est d’abord traité par le fournisseur de services d’urgence pour vérifier l’emplacement avant d’être routé vers l’opérateur de sécurité publique (PSAPI) (c’est-à-dire, l’opérateur 911).
        
          - **Non requis**   l’utilisateur n’est pas invité à entrer un emplacement. Lorsqu’un appel est effectué sans informations d’emplacement, le prestataire de services d’urgence répond à l’appel et demande un emplacement.
        
          - **Exclusion de responsabilité**   cette option est identique à la **condition requise** , sauf que l’utilisateur ne peut pas ignorer l’invite sans entrer d’informations d’emplacement. L’utilisateur peut toujours terminer un appel d’urgence, mais aucun autre appel ne peut être effectué sans entrer les informations. De plus, le texte de renonciation est affiché à l’utilisateur qui peut les informer des conséquences du refus d’entrer les informations d’emplacement. Pour définir le texte de l’exclusion de responsabilité, vous devez utiliser Skype entreprise Server Management Shell pour exécuter l’applet de cmdlet **Set-CsLocationPolicy** ou l’applet de **nouvelle-CsLocationPolicy** à l’aide du paramètre EnhancedEmergencyServiceDisclaimer. Pour plus d’informations, consultez la rubrique [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) ou [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy).
          
    
      - **Utiliser l’emplacement pour les services d’urgence uniquement** Skype entreprise peut utiliser les informations de géolocalisation pour différentes raisons (par exemple, pour informer les membres de votre emplacement actuel). Activez cette case à cocher pour vous assurer que les informations d’emplacement ne sont disponibles que pour les appels d’urgence.
    
      - **Utilisation PSTN utilisation**   de réseau téléphonique commuté (PSTN) qui sera utilisée pour déterminer le numéro de téléphone à utiliser pour diriger les appels d’urgence de clients à l’aide de ce profil. L’itinéraire associé à cette utilisation doit pointer vers un Trunk SIP dédié aux appels d’urgence ou à une passerelle ELIN (Emergency Identification Number) qui route les appels d’urgence vers le point de réponse de sécurité publique le plus proche (PSAPI).
    
      - **Numéro**   de téléphone d’urgence le numéro numéroté pour joindre les services d’urgence. Aux États-Unis, cette valeur est 911. La chaîne doit être effectuée sur les chiffres 0 à 9 et comporter entre 1 et 10 chiffres.
    
      - **Masque**   de numérotation d’urgence il s’agit d’un numéro que vous souhaitez traduire en valeur de la valeur numéro de téléphone d’urgence lors de la numérotation. Par exemple, si vous entrez une valeur 212 dans ce champ et que le champ numéro de téléphone d’urgence a la valeur 911, si un utilisateur compose le numéro 212, l’appel est effectué sur 911. Cela permet d’appeler d’autres numéros d’urgence et de toujours avoir accès aux services d’urgence (par exemple, si un membre d’un pays ou d’une région dont le numéro de téléphone est différent pour composer le numéro de votre pays ou de votre région, et non le numéro de la pays ou région dans lequel ils se trouvent actuellement). Vous pouvez définir plusieurs masques de numérotation d’urgence en séparant les valeurs par des points-virgules. Par exemple, 212; 414. La longueur maximale de la chaîne est de 100 caractères. Chaque caractère doit être un chiffre compris entre 0 et 9.
      

        > [!IMPORTANT]  
        > Assurez-vous que la valeur de masque de numérotation spécifiée n’est pas identique à un nombre dans une plage de stationnement d’appel. Le routage du parc d’appels est prioritaire par rapport à la conversion des chaînes de numérotation d’urgence. Pour afficher les plages d’orbites du parc d’appels, cliquez sur **fonctionnalités vocales** dans la barre de navigation gauche, puis cliquez sur **parc d’appels**. 

    
      - **URI de notification URI**   (Uniform Resource Identifiers) SIP pour être averti en cas d’appel d’urgence. Par exemple, le Bureau de sécurité de la société peut être notifié par un message instantané dès qu’un appel d’urgence est effectué. Si l’emplacement de l’appelant est disponible, il sera inclus dans la notification. Plusieurs URI SIP peuvent être inclus en tant que liste séparée par des virgules. Par exemple, «SIP: security@litwareinc.com», «SIP: kmyer@litwareinc.com». Les listes de distribution sont prises en charge. La chaîne doit contenir entre 1 et 256 caractères et doit commencer par le préfixe «SIP:». Avant de cliquer dans le champ URI de notification, un exemple s’affiche.
    
      - **URI de conférence**   il s’agit du numéro de téléphone d’un fournisseur de services de conférence rendez-vous pour les appels d’urgence. Par exemple, le Bureau de sécurité de la société peut recevoir un appel lors de la mise en place d’un appel d’urgence et écouter ou participer à cet appel (en fonction de la valeur fournie dans le champ **mode de conférence** ). La chaîne doit avoir entre 1 et 256 caractères de longueur et doit commencer par le préfixe SIP:. Un exemple s’affiche jusqu’à ce que vous cliquiez dans ce champ.
    
      - **Mode**   Conférence si vous spécifiez une valeur dans le champ **URI de conférence** , le **mode conférence** détermine si une tierce personne peut participer à l’appel ou si elle peut uniquement écouter. Spécifiez l’une des options suivantes:
        
          - **** Une personne tierce peut écouter uniquement la conversation entre l’appelant et l’opérateur PSAPI.   
        
          - **Deux sens**   de la partie tierce peuvent écouter l’appel et y participer entre l’appelant et l’opérateur PSAPI.

6.  Cliquez sur **Valider**.


    > [!IMPORTANT]  
    > Lorsque vous créez une stratégie d’utilisateur, elle ne s’applique initialement à aucun utilisateur ou site réseau. Pour appliquer la stratégie à un utilisateur, cliquez sur **utilisateurs** dans la barre de navigation gauche. Recherchez l’utilisateur auquel vous voulez appliquer la stratégie. Dans le menu **Edition**, cliquez sur **Afficher les détails**. Dans la page **modifier l’utilisateur du serveur** , sélectionnez la nouvelle stratégie d’emplacement dans la liste déroulante Stratégie d' **emplacement** , puis cliquez sur **valider**.<BR>Pour appliquer la stratégie à un site réseau, cliquez sur **configuration du réseau** dans la barre de navigation gauche, puis cliquez sur **site**. Recherchez le site réseau auquel vous voulez appliquer la stratégie. Dans le menu **Edition**, cliquez sur **Afficher les détails**. Dans **modifier le site**, sélectionnez la nouvelle stratégie d’emplacement dans la liste déroulante **stratégie d’emplacement** , puis cliquez sur **valider**.


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a>Pour modifier une stratégie d’emplacement dans le panneau de configuration Skype entreprise Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **stratégie d’emplacement**.

4.  Dans la page de **stratégie d’emplacement** , sélectionnez la stratégie d’emplacement que vous voulez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **modifier la stratégie d’emplacement** , modifiez les champs comme vous le souhaitez (pour plus d’informations, reportez-vous à l’étape 5 de la section «pour créer une stratégie d’emplacement» plus haut dans cette rubrique).

7.  Cliquez sur **Valider**.

        
## <a name="delete-a-location-policy"></a>Supprimer une stratégie d’emplacement


1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **stratégie d’emplacement**.

4.  Dans la page de **stratégie d’emplacement** , sélectionnez la stratégie d’emplacement que vous voulez supprimer.
   
    > [!NOTE]  
    > Vous pouvez supprimer plusieurs stratégies d’emplacement à la fois. Pour cela, appuyez sur CTRL et sélectionnez plusieurs stratégies tout en maintenant la touche CTRL enfoncée. Vous pouvez sélectionner toutes les stratégies dans le **** menu **Edition** .


5.  Dans le menu **modifier** , cliquez sur **supprimer**.

6.  Cliquez sur **OK**.

    > [!IMPORTANT]  
    > La stratégie d’emplacement global ne peut pas être supprimée. Si vous tentez de supprimer la stratégie globale, vous recevez un message d’avertissement indiquant que la stratégie sera réinitialisée à ses valeurs par défaut.


## <a name="see-also"></a>Voir aussi

[Créer ou modifier des sites réseau](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[Nouveau-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  

[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 
 
[Remove-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  

[Get-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
