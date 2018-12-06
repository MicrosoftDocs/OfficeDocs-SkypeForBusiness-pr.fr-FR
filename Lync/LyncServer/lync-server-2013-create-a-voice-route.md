---
title: Créer un itinéraire de communications vocales dans Lync Server 2013
TOCTitle: Créer un itinéraire de communications vocales dans Lync Server 2013
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398898(v=OCS.15)
ms:contentKeyID: 49298928
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer un itinéraire de communications vocales dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

La section suivante décrit la procédure de création d’un itinéraire de communications vocales à l’aide du Panneau de configuration Lync Server 2013. Pour modifier un itinéraire, voir la procédure décrite dans [Modifier un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).

## Pour créer un itinéraire de communications vocales à l’aide du Panneau de configuration Lync Server

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.

4.  Cliquez sur **Itinéraire**.

5.  Cliquez sur **Nouveau** pour afficher la boîte de dialogue **Nouvel itinéraire de communications vocales**.

6.  Dans **Nom**, tapez un nom descriptif pour l’itinéraire de communications vocales.

7.  (Facultatif) Dans **Description**, tapez une description supplémentaire du nouvel itinéraire de communications vocales.

8.  Pour spécifier les modèles que cet itinéraire doit prendre en charge, vous pouvez générer une expression régulière à l’aide de l’outil **Créer un modèle à suivre**, ou l’écrire manuellement.
    
      - Pour utiliser l’outil **Créer un modèle à suivre** afin de générer une expression régulière, entrez les valeurs comme suit. Vous pouvez spécifier deux types de correspondance de modèles :
        
          - **Chiffres de début des numéros que vous souhaitez autoriser** : entrez les valeurs de préfixe que cet itinéraire doit prendre en charge (y compris le + à gauche si nécessaire). Tapez par exemple **+425**, puis cliquez sur **Ajouter**. Renouvelez cette procédure pour chaque valeur de préfixe à inclure dans l’itinéraire.
        
          - **Exceptions** : si vous souhaitez spécifier une ou plusieurs exceptions pour une valeur de préfixe, mettez le préfixe en surbrillance et cliquez sur **Exceptions**. Tapez une ou plusieurs valeurs pour les modèles correspondants que cet itinéraire ne doit *pas* prendre en charge. Par exemple, pour exclure de l’itinéraire les numéros commençant par +425237, entrez la valeur **+425237** dans le champ **Exceptions**, puis cliquez sur **OK**.
    
      - Pour définir le modèle de correspondance manuellement, cliquez sur **Modifier** dans l’outil **Créer un modèle à suivre**, puis saisissez une expression régulière .NET Framework afin de spécifier le modèle de correspondance pour les numéros de téléphone de destination auxquels l’itinéraire est appliqué. Pour plus de détails sur la façon d’écrire des expressions régulières, voir « Expressions régulières .NET Framework » à l’adresse [http://go.microsoft.com/fwlink/?linkid=140927\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=140927%26clcid=0x40c).

9.  Sélectionnez l’option **Supprimer l’ID de l’appelant** si vous ne souhaitez pas que l’ID du téléphone à l’origine de l’appel sortant soit affiché au destinataire. Si vous sélectionnez cette option, vous devez spécifier un **Autre ID de l’appelant** qui apparaîtra sur l’affichage de l’ID d’appelant du destinataire.

10. Pour associer une ou plusieurs jonctions à l’itinéraire de communications vocales, cliquez sur **Ajouter**, puis sélectionnez une jonction dans la liste.
    
    > [!NOTE]  
    > Si votre déploiement comprend des serveurs de médiation Microsoft Office Communications Server 2007 R2, ils seront également disponibles dans la liste.

11. Pour associer une ou plusieurs utilisations PSTN (réseau téléphonique commuté) à l’itinéraire de communications vocales, cliquez sur **Sélectionner** et choisissez un enregistrement dans la liste des enregistrements d’utilisation PSTN définis pour votre déploiement de Voix Entreprise.
    
    > [!NOTE]  
    > Pour afficher les propriétés de chacun des enregistrements d’utilisation PSTN disponibles, voir <a href="lync-server-2013-view-pstn-usage-records.md">Affichage des enregistrements d’utilisation RTC dans Lync Server 2013</a>.<br />
    Pour créer ou modifier les enregistrements d’utilisation PSTN, voir <a href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Créer une stratégie et voix et configurer les enregistrements d’utilisation PSTN dans Lync Server 2013</a> ou <a href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013</a>.

12. Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour changer la position d’un enregistrement dans la liste, sélectionnez le nom de l’enregistrement, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    > [!NOTE]  
    > Contrairement à une stratégie de voix, l’ordre dans lequel les enregistrements d’utilisation PSTN sont répertoriés dans l’itinéraire de communications vocales n’a pas d’importance. Nous vous recommandons toutefois d’organiser la liste par fréquence d’utilisation. Par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Lync Server parcourt la liste du haut vers le bas.)

13. (Facultatif) Tapez une valeur dans le champ **Entrez un numéro traduit à tester** et cliquez sur **OK**. Les résultats du test sont affichés sous le champ.
    
    > [!NOTE]  
    > Vous pouvez enregistrer un itinéraire de communications vocales qui ne réussit pas encore le test, puis le reconfigurer par la suite. Pour plus d’informations, voir <a href="lync-server-2013-test-voice-routing.md">Test du routage des communications vocales dans Lync Server 2013</a>.

14. Cliquez sur **OK** pour enregistrer l’itinéraire de communications vocales.

> [!IMPORTANT]  
> Quand vous créez un itinéraire de communications vocales, vous devez exécuter la commande <strong>Valider tout</strong> pour publier la configuration modifiée. Pour plus d’informations, voir <a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</a>.

## Voir aussi

#### Tâches

[Modifier un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md)  
[Affichage des enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Créer une stratégie et voix et configurer les enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### Autres ressources

[Test du routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)

