---
title: "Mod. une strat. de voix et conf. des enr. d’util. PSTN dans Lync Server 2013"
TOCtitle: "Mod. une strat. de voix et conf. des enr. d’util. PSTN dans Lync Server 2013"
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398511(v=OCS.15)
ms:contentKeyID: 49297520
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Si vous souhaitez modifier une stratégie de voix, procédez comme suit. Pour créer une nouvelle stratégie de voix, voir la procédure décrite dans [Créer une stratégie et voix et configurer les enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md).

> [!NOTE]  
> Si un utilisateur est affecté à une stratégie de voix à laquelle aucun enregistrement d’utilisation du réseau téléphonique commuté (PSTN) n’est associé, l’utilisateur ne peut pas effectuer d’appels sortants. Pour obtenir la liste de tous les enregistrements d’utilisation PSTN disponibles dans votre déploiement Voix Entreprise et consulter leurs propriétés, voir <a href="lync-server-2013-view-pstn-usage-records.md">Affichage des enregistrements d’utilisation RTC dans Lync Server 2013</a>.

## Pour modifier une stratégie de voix

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Stratégie de la voix**.

4.  Dans la page **Stratégie de la voix**, double-cliquez sur le nom d’une stratégie de voix.
    
    > [!NOTE]  
    > L’étendue et le nom ont été définis lors de la création de la stratégie de voix. Ils ne peuvent pas être modifiés.

5.  (Facultatif) Dans **Modifier la stratégie de voix**, entrez d’autres informations décrivant la stratégie de voix.

6.  Activez ou désactivez les cases à cocher suivantes, afin d’activer ou de désactiver chacune des **Fonctionnalités d’appel** :
    
      - **Échappement de la messagerie vocale** empêche les appels d’être immédiatement acheminés au système de messagerie vocale du téléphone mobile de l’utilisateur lorsque la sonnerie simultanée est configurée et que le téléphone est éteint, en panne de batterie ou hors de portée.
        
        > [!NOTE]  
        > Cette fonctionnalité est uniquement configurable par le biais de Lync Server Management Shell.    
      - **Transfert d’appel** permet aux utilisateurs de transférer des appels vers d’autres téléphones et périphériques clients. Lync Server 2013 propose une gamme d’options de configuration beaucoup plus importante pour le transfert d’appel. Par exemple, si une organisation ne souhaite pas autoriser le transfert des appels entrants à l’extérieur vers le réseau téléphonique commuté (PSTN), un administrateur peut appliquer une stratégie de voix spéciale pour déployer cette restriction. Activée par défaut.
    
      - **Délégation** permet aux utilisateurs de spécifier d’autres utilisateurs pouvant passer et recevoir des appels à leur place. Dans Lync Server 2013, un délégué peut configurer la sonnerie simultanée pour que les appels entrants destinés à son responsable sonnent sur toutes les cibles de sonnerie simultanée du délégué. Le délégué peut ainsi répondre avec une plus grande souplesse aux appels destinés au responsable. Activée par défaut.
    
      - **Transfert d’appel** permet aux utilisateurs de transférer des appels à d’autres utilisateurs. Activée par défaut.
    
      - **Parcage d’appel** permet aux utilisateurs de parquer des appels en attente, puis de les reprendre depuis un autre téléphone ou client. Désactivée par défaut.
    
      - **Sonnerie simultanée** permet aux appels entrants de sonner sur des téléphones supplémentaires (par exemple, un téléphone mobile) ou d’autres périphériques de système d’extrémité. Lync Server 2013 propose une gamme d’options de configuration beaucoup plus importante pour la sonnerie simultanée. Activée par défaut.
    
      - **Appel d’équipe** permet aux utilisateurs d’une équipe définie de répondre aux appels destinés à d’autres membres de l’équipe. Activée par défaut.
    
      - **Réacheminement PSTN** permet aux appels des utilisateurs (auxquels cette stratégie est affectée) destinés à d’autres utilisateurs de l’entreprise d’être réacheminés sur le réseau téléphonique commuté (PSTN) si le réseau étendu (WAN) est saturé ou indisponible. Activée par défaut.
    
      - **Remplacement de stratégie de bande** permet aux administrateurs de remplacer les décisions de stratégie de contrôle d’admission des appels (CAC) pour un utilisateur particulier. Désactivée par défaut.
        
        > [!NOTE]  
        > La stratégie est uniquement remplacée pour les appels entrants vers l’utilisateur et non pour les appels sortants qui sont passés par l’utilisateur. Une fois la session établie, la consommation de bande passante est précisément enregistrée. Ce paramètre doit être utilisé avec modération.    
      - **Suivi des appels malveillants** permet aux utilisateurs de consigner des appels malveillants (comme une alerte à la bombe) à l’aide de l’interface utilisateur du client, qui signale ensuite ces appels dans les enregistrements des détails des appels (CDR). Désactivée par défaut.

7.  Afin d’associer et de configurer des enregistrements d’utilisation PSTN pour cette stratégie de voix, effectuez l’une des opérations suivantes :
    
      - Pour choisir un ou plusieurs enregistrements dans une liste de tous les enregistrements d’utilisation PSTN disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette stratégie de voix, puis cliquez sur **OK**.
    
      - Pour supprimer un enregistrement d’utilisation PSTN de cette stratégie de voix, sélectionnez l’enregistrement et cliquez sur **Supprimer**.
    
      - Pour définir un nouvel enregistrement d’utilisation PSTN et l’associer à cette stratégie de voix, procédez comme suit :
        
        1.  Cliquez sur **Nouveau**.
        
        2.  Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement. Par exemple, vous pouvez créer un enregistrement d’utilisation PSTN appelé **Redmond** pour les employés qui travaillent à plein temps situés à Redmond et un autre enregistrement appelé **RedmondTemps** pour les employés qui travaillent à temps partiel.
            
            > [!NOTE]  
            > Le nom de l’enregistrement d’utilisation PSTN doit être unique dans le déploiement Voix Entreprise. Une fois que l’enregistrement est enregistré, le champ <strong>Nom</strong> ne peut plus être modifié.        
        3.  Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :
            
              - Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.
            
              - Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.
            
              - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, voir [Créer un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, voir [Modifier un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Cliquez sur **OK**.
    
      - Pour modifier un enregistrement d’utilisation PSTN qui est déjà associé à cette stratégie de voix, procédez comme suit :
        
        1.  Sélectionnez l’enregistrement d’utilisation PSTN à modifier, puis cliquez sur **Afficher les détails**.
        
        2.  Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :
            
              - Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.
            
              - Pour supprimer un itinéraire de cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.
            
              - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, voir [Créer un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, voir [Modifier un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Cliquez sur **OK**.

8.  Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour changer la position d’un enregistrement dans la liste, sélectionnez le nom de l’enregistrement, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    > [!NOTE]  
    > L’ordre dans lequel les enregistrements d’utilisation apparaissent dans la stratégie de voix est essentiel. Lync Server parcourt la liste de haut en bas. Nous vous conseillons d’organiser la liste par fréquence d’utilisation ; par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

9.  Afin d’associer et de configurer des enregistrements d’utilisation PSTN pour le transfert d’appel et la sonnerie simultanée dans cette stratégie de voix, effectuez l’une des opérations suivantes :
    
      - Pour utiliser les mêmes enregistrements d’utilisation PSTN pour le transfert d’appel et la sonnerie simultanée que cette stratégie de voix, sélectionnez l’option **Routage avec les utilisations PSTN d’appel** dans le menu déroulant.
    
      - Pour autoriser uniquement le transfert d’appel et la sonnerie simultanée vers des utilisateurs Lync internes, sélectionnez **Routage uniquement vers des utilisateurs Lync internes** dans le menu déroulant. Les appels ne seront pas transférés à des numéros PSTN externes.
    
      - Pour spécifier des enregistrements d’utilisation PSTN pour le transfert d’appel et la sonnerie simultanée différents de ceux utilisés pour cette stratégie de voix, sélectionnez l’option **Routage avec des utilisations PSTN personnalisées** dans le menu déroulant. Cette option affiche un contrôle pour sélectionner les enregistrements d’utilisation PSTN existants ou créer de nouveaux enregistrements d’utilisation PSTN spécifiquement pour le transfert d’appel et la sonnerie simultanée.
        
          - Pour choisir un ou plusieurs enregistrements dans une liste d’enregistrements d’utilisation PSTN pour le transfert d’appel et la sonnerie simultanée, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette stratégie de transfert d’appel et de sonnerie simultanée, puis cliquez sur **OK**.
        
          - Pour supprimer un enregistrement d’utilisation PSTN de cette stratégie de transfert d’appel et de sonnerie simultanée, sélectionnez l’enregistrement et cliquez sur **Supprimer**.
        
          - Pour définir un nouvel enregistrement d’utilisation PSTN et l’associer à cette stratégie de transfert d’appel et de sonnerie simultanée, procédez comme suit :
            
            1.  Cliquez sur **Nouveau**.
            
            2.  Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement.
                
                > [!NOTE]  
                > Le nom de l’enregistrement d’utilisation PSTN doit être unique dans le déploiement Voix Entreprise. Une fois que l’enregistrement est enregistré, le champ <strong>Nom</strong> ne peut plus être modifié.            
            3.  Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :
                
                  - Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.
                
                  - Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.
                
                  - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, voir [Créer un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, voir [Modifier un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            4.  Cliquez sur **OK**.
        
          - Pour modifier un enregistrement d’utilisation PSTN qui est déjà associé à cette stratégie de voix, procédez comme suit :
            
            1.  Sélectionnez l’enregistrement d’utilisation PSTN à modifier, puis cliquez sur **Afficher les détails**.
            
            2.  Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :
                
                  - Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.
                
                  - Pour supprimer un itinéraire de cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.
                
                  - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, voir [Créer un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, voir [Modifier un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            3.  Cliquez sur **OK**.

10. (Facultatif) Entrez un numéro pour tester la stratégie de voix, puis cliquez sur **OK**. Les résultats du test apparaissent sous **Numéro traduit à tester**.
    
    > [!NOTE]  
    > Vous pouvez enregistrer une stratégie de voix qui ne réussit pour l’instant pas le test, puis la reconfigurer ultérieurement. Pour plus d’informations, voir <a href="lync-server-2013-test-voice-routing.md">Test du routage des communications vocales dans Lync Server 2013</a>.

11. Cliquez sur **OK**.

12. Dans la page **Stratégie de la voix**, cliquez sur **Valider**, puis sur **Valider tout**.
    
    > [!NOTE]  
    > Chaque fois que vous créez ou modifiez une stratégie de voix, vous devez exécuter la commande <strong>Valider tout</strong> pour publier la modification de la configuration. Pour plus d’informations, voir <a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</a> dans la documentation des opérations.

13. (Facultatif) L’échappement de la messagerie vocale détecte qu’un appel a été immédiatement pris en charge par la messagerie vocale du téléphone mobile de l’utilisateur et déconnecte l’appel vers la messagerie vocale du téléphone mobile. Cela permet à l’appel de continuer de sonner sur les autres systèmes d’extrémité de l’utilisateur, donnant ainsi à l’utilisateur la possibilité de répondre à l’appel. Pour plus d’informations sur la façon de configurer une stratégie de messagerie vocale, voir [Configuration de la redirection vers la messagerie vocale dans Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).

## Voir aussi

#### Tâches

[Créer une stratégie et voix et configurer les enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Affichage des enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Créer un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md)  
[Modifier un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md)  
[Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[Configuration de la redirection vers la messagerie vocale dans Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md)  

#### Autres ressources

[Test du routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)

