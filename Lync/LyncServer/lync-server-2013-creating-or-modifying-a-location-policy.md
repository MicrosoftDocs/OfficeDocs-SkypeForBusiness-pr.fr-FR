---
title: Création ou modification d’une stratégie d’emplacement
TOCTitle: Création ou modification d’une stratégie d’emplacement
ms:assetid: 10338418-4da4-42df-b231-f52098c08dae
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687971(v=OCS.15)
ms:contentKeyID: 49891234
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification d’une stratégie d’emplacement

 

_**Dernière rubrique modifiée :** 2012-11-01_

Dans Lync Server 2013, vous pouvez utiliser la stratégie d’emplacement pour appliquer des paramètres liés au système Enhanced 9-1-1 (E9-1-1) et des paramètres d’emplacement pour les utilisateurs et les contacts. La stratégie d’emplacement détermine si un utilisateur peut avoir recours au système E9-1-1 et, le cas échéant, le comportement d’un appel d’urgence. Par exemple, la stratégie d’emplacement permet de définir le numéro d’appel d’urgence (par exemple, 911 aux États-Unis, 15 en France), de déterminer si le service de sécurité de l’entreprise doit être automatiquement averti et comment l’appel doit être acheminé.

Vous pouvez configurer des stratégies d’emplacement depuis le groupe **Configuration réseau** dans le Panneau de configuration Lync Server 2013. Le Panneau de configuration Lync Server vous permet d’afficher, de créer, de modifier ou de supprimer des stratégies d’emplacement. Suivez les procédures indiquées dans cette section pour créer ou modifier une stratégie d’emplacement. Pour plus d’informations sur la suppression des stratégies d’emplacement, voir [Suppression d’une stratégie d’emplacement](lync-server-2013-deleting-a-location-policy.md).

Dans Lync Server 2013, vous pouvez remplacer la durée par défaut entre les demandes clientes pour la mise à jour de l’emplacement du service d’informations sur l’emplacement. La valeur par défaut s’élève à 4 heures. Utilisez l’applet de commande **Set-CsLocationPolicy** avec le paramètre LocationRefreshInterval pour remplacer la valeur par défaut.

## Pour créer une stratégie d’emplacement dans Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie d’emplacement**.

4.  Dans la page **Stratégie d’emplacement**, cliquez sur **Nouveau**, puis sélectionnez le type de stratégie que vous souhaitez créer :
    
      - Pour créer une stratégie de site, cliquez sur **Stratégie du site**. Dans **Sélectionner un site**, choisissez le site auquel vous souhaitez appliquer la stratégie et cliquez sur **OK**. Dans la page **Créer une stratégie d’emplacement**, le champ **Étendue** contient la valeur **Site** et le champ **Nom** contient le nom du site que vous avez choisi. Vous ne pouvez modifier aucun de ces champs. Une stratégie de site est automatiquement appliquée à tous les utilisateurs sur le site spécifié et remplace la stratégie globale qui leur était appliquée.
    
      - Pour créer une **stratégie de l’utilisateur**, cliquez sur **Stratégie de l’utilisateur**. Dans la page **Créer une stratégie d’emplacement**, le champ **Étendue** contient la valeur **Utilisateur**. Vous ne pouvez pas modifier cette valeur. Dans le champ **Nom**, tapez le nom que vous souhaitez donner à cette stratégie. Une stratégie de l’utilisateur ne s’applique pas automatiquement aux utilisateurs. Après avoir créé la stratégie de l’utilisateur, vous devez manuellement octroyer la stratégie aux utilisateurs ou aux sites réseau auxquels vous souhaitez que la stratégie s’applique.

5.  Renseignez les champs restants, comme suit :
    
      - **Activer les services d’urgence avancés**   Activez cette case à cocher pour activer ces services pour les utilisateurs associés à la stratégie relative au système E9-1-1. Lorsque les services d’urgence sont activés, les clients Lync Server récupèrent les informations d’emplacement lors de leur inscription à un emplacement et incluent ces informations lors de la réception d’un appel d’urgence.
    
      - **Emplacement**   Spécifiez l’une des valeurs suivantes :
        
          - **Requis**   L’utilisateur est invité à fournir des informations sur l’emplacement lorsque le client s’inscrit à un nouvel emplacement. L’utilisateur peut ignorer l’invite sans fournir aucune information. S’il fournit des informations, le fournisseur de services d’urgence répond d’abord à l’appel d’urgence pour vérifier l’emplacement, puis l’appel est transmis à l’opérateur du centre d’appels de la sécurité publique (c’est-à-dire l’opérateur des services d’urgence).
        
          - **Non requis**   L’utilisateur n’est pas invité à saisir un emplacement. Lorsqu’un appel est effectué sans informations d’emplacement, le fournisseur de services d’urgence y répond et demande qu’un emplacement lui soit indiqué.
        
          - **Clause d’exclusion de responsabilité**   Cette option est la même que **Requis** sauf que l’utilisateur ne peut pas ignorer l’invite sans fournir des informations sur l’emplacement. L’utilisateur peut toujours appeler les services d’urgence, mais aucun autre appel ne peut être passé sans fournir les informations. De plus, un texte d’exclusion s’affiche pour informer l’utilisateur des conséquences du refus de fournir des informations sur l’emplacement. Pour définir le texte d’exclusion de responsabilité, vous devez utiliser Lync Server Management Shell pour exécuter l’applet de commande **Set-CsLocationPolicy** ou l’applet de commande **New-CsLocationPolicy** avec le paramètre EnhancedEmergencyServiceDisclaimer. Pour plus d’informations, voir [Set-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsLocationPolicy) ou [New-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsLocationPolicy) dans la documentation de Lync Server Management Shell.
            
            > [!NOTE]  
            > Dans Lync Server 2013, vous pouvez utiliser la stratégie d’emplacement pour définir différentes clauses d’exclusion pour différents paramètres régionaux ou différents ensembles d’utilisateurs, contrairement à Lync Server 2010 où vous ne pouviez spécifier qu’une clause d’exclusion globale pour toute l’organisation.    
      - **Utiliser l’emplacement pour les services d’urgence uniquement**   Lync peut utiliser les informations d’emplacement pour diverses raisons (par exemple, pour indiquer votre emplacement à vos collègues). Activez cette case à cocher pour que les informations sur l’emplacement soient uniquement disponibles lors d’un appel d’urgence.
    
      - **Utilisation PSTN**   Réseau téléphonique commuté public qui permettra de déterminer l’itinéraire des communications vocales afin de router les appels d’urgence des clients à l’aide de ce profil. L’itinéraire associé à cette utilisation doit pointer sur une jonction SIP dédiée aux appels d’urgence ou à une passerelle ELIN (Emergency Location Identification Number) qui route les appels d’urgence vers le centre téléphonique de sécurité publique (Public Safety Answering Point ou PSAP) le plus proche.
    
      - **Numéro d’urgence**   Numéro qui est composé pour joindre les services d’urgence. Aux États-Unis il s’agit du 911. La chaîne doit être composée des chiffres 0 à 9 et peut avoir une longueur comprise entre 1 et 10 chiffres.
    
      - **Masque de numéro d’urgence**   Numéro que vous voulez traduire en valeur de numéro d’urgence lorsqu’il est composé. Par exemple, si vous entrez 212 dans ce champ et si la valeur du champ Numéro d’urgence est 911, le numéro appelé sera le 911 si un utilisateur compose le 212. Cela permet de composer d’autres numéros d’urgence et de pouvoir joindre quand même les services d’urgence (par exemple, si une personne provenant d’un pays où le numéro d’urgence est différent tente de composer ce numéro au lieu du numéro du pays dans lequel elle se trouve actuellement). Vous pouvez définir plusieurs masques d’appel d’urgence en séparant les valeurs par des points-virgules. Par exemple, 212;414. La longueur maximale de la chaîne est 100 caractères. Chaque caractère doit être un chiffre compris entre 0 et 9.
        
        > [!IMPORTANT]  
        > Assurez-vous que la valeur du masque d’appel n’est pas identique à un numéro figurant dans une plage de numéros d’appels parqués. Le routage du parcage d’appels aura priorité sur la conversion des chaînes d’appel d’urgence. Pour afficher les plages de numéros d’appels parqués, cliquez sur <strong>Fonctionnalités vocales</strong> dans la barre de navigation de gauche, puis cliquez sur <strong>Parcage d’appel</strong>. Pour plus d’informations, voir <a href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">Configurer les extensions de numéro de téléphone pour le parcage d’appel</a>.    
      - **URI de notification**   Un ou plusieurs URI (Uniform Resource Identifier) SIP à notifier lorsqu’un appel d’urgence est passé. Par exemple, le service de sécurité de l’entreprise peut être notifié par un message instantané pour chaque appel d’urgence. Si l’emplacement de l’appelant est disponible, cet emplacement sera inclus dans la notification. Plusieurs URI SIP peuvent être insérés dans une liste dans laquelle ils sont séparés par des virgules. Par exemple, « sip:security@litwareinc.com »,« sip:kmyer@litwareinc.com ». Les listes de distribution sont prises en charge. La chaîne doit comporter entre 1 et 256 caractères et commencer par le préfixe « sip: ». Avant que vous ne cliquiez dans le champ URI de notification un exemple est affiché.
    
      - **URI de la conférence**   URI SIP, dans ce cas le numéro de téléphone d’une tierce personne qui sera invitée à participer aux appels d’urgence. Par exemple, le service de sécurité de l’entreprise peut recevoir un appel l’invitant à écouter ou à participer à un appel d’urgence (en fonction de la valeur fournie dans le champ **Mode conférence**). La chaîne doit comporter entre 1 et 256 caractères et commencer par le préfixe sip:. Un exemple est affiché avant que vous ne cliquiez dans ce champ.
    
      - **Mode conférence**   Si vous spécifiez une valeur dans le champ **URI de la conférence**, le **mode conférence** détermine si une tierce personne peut participer à l’appel d’urgence ou seulement l’écouter. Spécifiez une des options suivantes :
        
          - **Unidirectionnel**   La personne tierce peut uniquement écouter la conversation entre l’appelant et l’opérateur du centre d’appels de la sécurité publique.
        
          - **Bidirectionnel**   Une tierce personne peut écouter et participer à l’appel entre l’appelant et l’opérateur du centre d’appels de la sécurité publique.

6.  Cliquez sur **Valider**.
    
    > [!IMPORTANT]  
    > Lorsque vous créez une stratégie utilisateur, cette stratégie ne s’applique initialement à aucun utilisateur ou site réseau. Pour appliquer la stratégie à un utilisateur, cliquez sur <strong>Utilisateurs</strong> dans la barre de navigation de gauche. Recherchez l’utilisateur auquel vous souhaitez appliquer la stratégie. Dans le menu <strong>Edition</strong>, cliquez sur <strong>Afficher les détails</strong>. Dans la page <strong>Modifier l’utilisateur Lync Server</strong>, sélectionnez la nouvelle stratégie d’emplacement dans la liste déroulante <strong>Stratégie d’emplacement</strong>, puis cliquez sur <strong>Valider</strong>.<br />
    Pour appliquer la stratégie à un site réseau, cliquez sur <strong>Configuration réseau</strong> dans la barre de navigation de gauche et cliquez sur <strong>Site</strong>. Recherchez le site réseau auquel vous souhaitez appliquer la stratégie. Dans le menu <strong>Edition</strong>, cliquez sur <strong>Afficher les détails</strong>. Dans <strong>Modifier le site</strong>, sélectionnez la nouvelle stratégie d’emplacement dans la liste déroulante <strong>Stratégie d’emplacement?</strong>, puis cliquez sur <strong>Valider</strong>.

## Pour modifier une stratégie d’emplacement dans Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie d’emplacement**.

4.  Dans la page **Stratégie d’emplacement**, sélectionnez la stratégie d’emplacement que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier la stratégie d’emplacement**, modifiez les champs comme il convient (pour plus d’informations, voir l’étape 5 dans la procédure de création d’une stratégie d’emplacement plus haut dans cette rubrique).

7.  Cliquez sur **Valider**.

## Voir aussi

#### Tâches

[Suppression d’une stratégie d’emplacement](lync-server-2013-deleting-a-location-policy.md)  

#### Concepts

[Définition de la stratégie d’emplacement pour Lync Server 2013](lync-server-2013-defining-the-location-policy.md)  

#### Autres ressources

[Configurer les extensions de numéro de téléphone pour le parcage d’appel](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)

