---
title: "Créer strat. et voix et conf. les enr. d’ut. PSTN dans Lync Server 2013"
TOCtitle: "Créer strat. et voix et conf. les enr. d’ut. PSTN dans Lync Server 2013"
ms:assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg399027(v=OCS.15)
ms:contentKeyID: 49299198
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer une stratégie et voix et configurer les enregistrements d’utilisation PSTN dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Procédez comme suit pour créer une stratégie de voix. Si vous souhaitez modifier une stratégie de voix, consultez la procédure de la rubrique [Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) (contenu éventuellement en anglais).

> [!NOTE]  
> Chaque stratégie de voix doit être associée à au moins un enregistrement d’utilisation réseau téléphonique commuté (PSTN). Pour obtenir la liste de tous les enregistrements d’utilisation PSTN disponibles dans votre déploiement Voix Entreprise et consulter leurs propriétés, voir <a href="lync-server-2013-view-pstn-usage-records.md">Affichage des enregistrements d’utilisation RTC dans Lync Server 2013</a> (contenu éventuellement en anglais).

## Pour créer une stratégie de voix

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Stratégie de la voix**.

4.  Dans la page **Stratégie de la voix**, cliquez sur **Nouveau** puis sélectionnez l’étendue de la nouvelle stratégie :
    
      - La **stratégie de site** s’applique à l’ensemble d’un site, à l’exception des utilisateurs ou groupes attribués à une stratégie d’utilisateur. Si vous sélectionnez l’étendue Site pour une stratégie, choisissez le site dans la boîte de dialogue **Sélectionner un site**. Si une stratégie de voix a déjà été créée pour un site, le site n’apparaît pas dans la boîte de dialogue **Sélectionner un site**.
    
      - Une **stratégie d’utilisateur** peut être appliquée à des utilisateurs ou à des groupes spécifiés.

5.  Si l’étendue de la stratégie de voix est Utilisateur, entrez un nom descriptif de la stratégie dans le champ **Nom**.
    
    > [!NOTE]  
    > Si l’étendue de la stratégie de voix est Site, le champ <strong>Nom</strong> de la boîte de dialogue <strong>Nouvelle stratégie de voix</strong> est prérempli avec le nom du site et ne peut pas être modifié.

6.  (Optionnel) Entrez une description supplémentaire de la stratégie de voix.

7.  Activez ou désactivez les cases à cocher suivantes pour activer ou désactiver chacune des **fonctionnalités d’appel** pour cette stratégie de voix :
    
      - **Voice mail escape** empêche les appels d’être immédiatement routés vers le système de messagerie vocale du téléphone mobile de l’utilisateur lorsque la sonnerie simultanée est configurée et que le téléphone est éteint, déchargé ou en dehors de la plage.
        
        > [!NOTE]  
        > Cette fonctionnalité peut uniquement être configurée via le Lync Server Management Shell    
      - **Transfert d’appels** permet aux utilisateurs de transférer des appels vers d’autres téléphones et périphériques clients. Lync Server 2013 offre un éventail bien plus large d’options de configuration pour le transfert d’appels. Par exemple, si une entreprise ne souhaite pas autoriser les appels entrants à être transférés de manière externe vers le PSTN, un administrateur peut appliquer une stratégie de voix spéciale pour déployer cette restriction. Activée par défaut.
    
      - **Délégation** permet aux utilisateurs de spécifier d’autres utilisateurs pouvant passer et recevoir des appels à leur place. Dans Lync Server 2013, un délégué peut configurer la sonnerie simultanée, qui permet de faire sonner tous les appels entrants pour son responsable sur toutes les cibles de sonnerie simultanée du délégué. Celui-ci bénéficie ainsi d’une plus grande flexibilité pour répondre aux appels destinés au responsable. Activée par défaut.
    
      - **Transfert d’appel** permet aux utilisateurs de transférer des appels à d’autres utilisateurs. Activée par défaut.
    
      - **Parcage d’appel** permet aux utilisateurs de parquer des appels en attente, puis de les reprendre depuis un autre téléphone ou client. Désactivée par défaut.
    
      - **Sonnerie simultanée** permet aux appels entrants de sonner sur des téléphones supplémentaires (par exemple, un téléphone portable) ou d’autres périphériques de système d’extrémité. Lync Server 2013 offre un éventail bien plus large d’options de configuration pour la sonnerie simultanée. Activée par défaut.
    
      - **Appel d’équipe** permet aux utilisateurs d’une équipe définie de répondre aux appels destinés à d’autres membres de l’équipe. Activée par défaut.
    
      - **Réacheminement PSTN** permet aux appels des utilisateurs (auxquels cette stratégie est affectée) destinés à d’autres utilisateurs de l’entreprise d’être réacheminés sur le réseau téléphonique commuté (PSTN) si le réseau étendu (WAN) est saturé ou indisponible. Activée par défaut.
    
      - Le **remplacement de stratégie de bande passante** permet aux administrateurs de remplacer les décisions de stratégie du contrôle d’admission des appels pour un utilisateur particulier. Désactivée par défaut.
        
        > [!NOTE]  
        > La stratégie sera uniquement remplacée pour les appels entrants vers l’utilisateur et non pour les appels sortants qui sont passés par l’utilisateur. Une fois la session établie, la consommation de bande passante est précisément enregistrée. Ce paramètre doit être utilisé avec modération et doit être réservé à la prise de décision appropriée en matière de contrôle d’admission des appels.    
      - **Suivi des appels malveillants** permet aux utilisateurs de consigner des appels malveillants (comme une alerte à la bombe) à l’aide de l’interface utilisateur du client, qui signale ensuite ces appels dans les enregistrements des détails des appels (CDR). Désactivée par défaut.

8.  Afin d’associer et de configurer des enregistrements d’utilisation PSTN pour cette stratégie de voix, effectuez l’une des opérations suivantes :
    
      - Pour choisir un ou plusieurs enregistrements dans une liste de tous les enregistrements d’utilisation PSTN disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**. Sélectionnez les enregistrements que vous voulez associer avec cette stratégie de voix, puis cliquez sur **OK**.
    
      - Pour supprimer un enregistrement d’utilisation PSTN de cette stratégie de voix, sélectionnez l’enregistrement et cliquez sur **Supprimer**.
    
      - Pour définir un nouvel enregistrement d’utilisation PSTN et l’associer à cette stratégie de voix, procédez comme suit :
        
        1.  Cliquez sur **Nouveau**.
        
        2.  Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement. Par exemple, vous pouvez créer un enregistrement d’utilisation PSTN appelé **Redmond** pour les employés qui travaillent à plein temps situés à Redmond et un autre appelé **RedmondTemps** pour les employés qui travaillent à temps partiel.
            
            > [!NOTE]  
            > Le nom de l’enregistrement d’utilisation PSTN doit être unique dans le déploiement Voix Entreprise. Une fois que l’enregistrement est enregistré, le champ <strong>Nom</strong> ne peut plus être modifié.        
        3.  Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :
            
              - Pour choisir un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous voulez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.
            
              - Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.
            
              - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, voir [Créer un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md) (contenu éventuellement en anglais).
            
              - Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, voir [Modifier un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md) (contenu éventuellement en anglais).
        
        4.  Cliquez sur **OK**.
    
      - Pour modifier un enregistrement d’utilisation PSTN qui est déjà associé à cette stratégie de voix, procédez comme suit :
        
        1.  Sélectionnez l’enregistrement d’utilisation PSTN que vous voulez modifier, puis cliquez sur **Afficher les détails**.
        
        2.  Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :
            
              - Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.
            
              - Pour supprimer un itinéraire de cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.
            
              - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, voir [Créer un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md) (contenu éventuellement en anglais).
            
              - Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, voir [Modifier un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md) (contenu éventuellement en anglais).
        
        3.  Cliquez sur **OK**.

9.  Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour changer la position d’un enregistrement dans la liste, sélectionnez le nom de l’enregistrement, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    > [!IMPORTANT]  
    > L’ordre dans lequel les enregistrements d’utilisation apparaissent dans la stratégie de voix est essentiel. Lync Server parcourt la liste de haut en bas. Nous vous conseillons d’organiser la liste par fréquence d’utilisation ; par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

10. Pour associer et configurer les enregistrements d’utilisation PSTN pour cette stratégie de voix, effectuez l’une des opérations suivantes :
    
      - Pour utiliser les mêmes enregistrements d’utilisation PSTN pour le transfert d’appels et la sonnerie simultanée que cette stratégie de voix, sélectionnez l’option **Acheminer à l’aide des utilisations PSTN d’appel** dans le menu déroulant.
    
      - Pour activer le transfert d’appels et la sonnerie simultanée pour les utilisateurs internes de Lync uniquement, sélectionnez l’option **Acheminer vers les utilisateurs internes de Lync uniquement** dans le menu déroulant. Les appels ne seront pas transférés vers des numéros PSTN externes.
    
      - Pour spécifier des enregistrements d’utilisation PSTN pour le transfert d’appels et la sonnerie simultanée différents de ceux utilisés pour cette stratégie de voix, sélectionnez l’option **Acheminer à l’aide d’utilisations PSTN personnalisées** dans le menu déroulant. Cette option affiche un contrôle pour sélectionner des enregistrements d’utilisation PSTN existants ou créer des enregistrements d’utilisation PSTN spécifiquement pour le transfert d’appels et la sonnerie simultanée.
        
          - Pour choisir un ou plusieurs enregistrements dans une liste des enregistrements d’utilisation PSTN pour le transfert d’appels et la sonnerie simultanée, cliquez sur **Sélectionner**. Sélectionnez les enregistrements que vous voulez associer à cette stratégie de transfert d’appels et de sonnerie simultanée, puis cliquez sur **OK**.
        
          - Pour supprimer un enregistrement d’utilisation PSTN de cette stratégie de transfert d’appels et de sonnerie simultanée, sélectionnez l’enregistrement et cliquez sur **Supprimer**.
        
          - Pour définir un nouvel enregistrement d’utilisation PSTN et l’associer à cette stratégie de transfert d’appels et de sonnerie simultanée, procédez comme suit :
            
            1.  Cliquez sur **Nouveau**.
            
            2.  Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement.
                
                > [!NOTE]  
                > Le nom de l’enregistrement d’utilisation PSTN doit être unique dans le déploiement Voix Entreprise. Une fois que l’enregistrement est enregistré, le champ <strong>Nom</strong> ne peut plus être modifié.            
            3.  Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :
                
                  - Pour choisir un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous voulez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.
                
                  - Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.
                
                  - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, voir [Créer un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md) (contenu éventuellement en anglais).
                
                  - Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, voir [Modifier un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md) (contenu éventuellement en anglais).
            
            4.  Cliquez sur **OK**.
        
          - Pour modifier un enregistrement d’utilisation PSTN déjà associé à cette stratégie de voix, procédez comme suit :
            
            1.  Sélectionnez l’enregistrement d’utilisation PSTN à modifier, puis cliquez sur **Afficher les détails**.
            
            2.  Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :
                
                  - Pour choisir un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.
                
                  - Pour supprimer un itinéraire de cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.
                
                  - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, voir [Créer un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md) (contenu éventuellement en anglais).
                
                  - Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, voir [Modifier un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md) (contenu éventuellement en anglais).
            
            3.  Cliquez sur **OK**.

11. (Facultatif) Entrez un numéro pour tester la stratégie de voix, puis cliquez sur **OK**. Les résultats du test apparaissent sous **Numéro traduit à tester**.
    
    > [!NOTE]  
    > Vous pouvez enregistrer une stratégie de voix qui ne réussit pour l’instant pas le test, puis la reconfigurer ultérieurement. Pour plus d’informations, voir <a href="lync-server-2013-test-voice-routing.md">Test du routage des communications vocales dans Lync Server 2013</a> (contenu éventuellement en anglais).

12. Cliquez sur **OK**.

13. Sur la page **Stratégie de la voix**, cliquez sur **Valider**, puis sur **Valider tout**.
    
    > [!NOTE]  
    > À chaque fois que vous créez ou modifiez une stratégie de voix, vous devez exécuter la commande <strong>Valider tout</strong> pour publier la modification de la configuration. Pour plus d’informations, voir <a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</a> (contenu éventuellement en anglais) dans la documentation relative aux opérations.

14. (Facultatif) Voicemail Escape détecte qu’un appel a été immédiatement intercepté par la messagerie vocale du téléphone portable de l’utilisateur, et déconnecte l’appel à la messagerie vocale du téléphone portable. L’appel continue ainsi de sonner sur les autres points de terminaison de l’utilisateur, lui offrant la possibilité de répondre. Pour plus d’informations sur la manière de configurer une stratégie de messagerie vocale, voir [Configuration de la redirection vers la messagerie vocale dans Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md) (contenu éventuellement en anglais).

## Voir aussi

#### Tâches

[Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Affichage des enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Créer un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md)  
[Modifier un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md)  
[Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[Configuration de la redirection vers la messagerie vocale dans Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md)  

#### Autres ressources

[Test du routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)

