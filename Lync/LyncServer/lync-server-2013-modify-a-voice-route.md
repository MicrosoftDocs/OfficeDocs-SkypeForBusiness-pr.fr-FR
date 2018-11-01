---
title: Modifier un itinéraire de communications vocales dans Lync Server 2013
TOCTitle: Modifier un itinéraire de communications vocales dans Lync Server 2013
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412838(v=OCS.15)
ms:contentKeyID: 49298555
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modifier un itinéraire de communications vocales dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Cette rubrique présente la procédure de modification d’un itinéraire des communications vocales. Pour créer un nouvel itinéraire, voir [Créer un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).

## Pour modifier un itinéraire de communications vocales

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Itinéraire**.

4.  Dans la page **Itinéraire**, utilisez l’une des méthodes suivantes pour modifier un itinéraire de communications vocales :
    
      - Sélectionnez un nom d’itinéraire de communications vocales, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
      - Sélectionnez un nom d’itinéraire de communications vocales, cliquez sur **Modifier**, puis sur **Copier** et enfin sur **Coller**. Sélectionnez la copie de l’itinéraire de communications vocales créée à l’instant, cliquez sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans la page **Modifier l’itinéraire de communications vocales**, dans le champ **Nom**, tapez un nom descriptif pour l’itinéraire de communications vocales.

6.  (Facultatif) Dans le champ **Description**, tapez une description supplémentaire du nouvel itinéraire de communications vocales.

7.  Pour spécifier les modèles que cet itinéraire doit prendre en charge, vous pouvez générer une expression régulière à l’aide de l’outil **Créer un modèle à suivre**, ou l’écrire manuellement.
    
      - Pour utiliser l’outil **Créer un modèle à suivre** afin de générer une expression régulière, entrez les valeurs comme suit. Vous pouvez spécifier deux types de correspondance de modèles :
        
          - **Chiffres de début des numéros que vous souhaitez autoriser** : Entrez les valeurs de préfixe que cet itinéraire doit prendre en charge (y compris le + à gauche si nécessaire). Tapez par exemple **+425**, puis cliquez sur **Ajouter**. Renouvelez cette procédure pour chaque valeur de préfixe à inclure dans l’itinéraire.
        
          - **Exceptions** : Si vous souhaitez spécifier une ou plusieurs exceptions pour une valeur de préfixe, mettez le préfixe en surbrillance et cliquez sur **Exceptions**. Tapez une ou plusieurs valeurs pour les modèles correspondants que cet itinéraire ne doit *pas* prendre en charge. Par exemple, pour exclure de l’itinéraire les numéros commençant par +425237, entrez la valeur **+425237** dans le champ **Exceptions**, puis cliquez sur **OK**.
    
      - Pour définir le modèle de correspondance manuellement, cliquez sur **Modifier** dans l’outil **Créer un modèle à suivre**, puis entrez une expression régulière .NET Framework afin de spécifier le modèle de correspondance pour les numéros de téléphone de destination auxquels l’itinéraire est appliqué. Pour plus d’informations sur la façon d’écrire des expressions régulières, voir « Expressions régulières .NET Framework » à l’adresse [http://go.microsoft.com/fwlink/?linkid=140927\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=140927%26clcid=0x40c).

8.  Sélectionnez l’option **Supprimer l’ID de l’appelant** si vous ne souhaitez pas que l’ID du téléphone à l’origine de l’appel sortant soit affiché au destinataire. Si vous sélectionnez cette option, vous devez spécifier un **Autre ID de l’appelant** qui apparaîtra sur l’affichage de l’ID d’appelant du destinataire.

9.  Pour associer une ou plusieurs jonctions RTC (réseau téléphonique commuté) à l’itinéraire des communications vocales, cliquez sur **Ajouter**, puis sélectionnez une jonction dans la liste.
    
    > [!NOTE]  
    > Si votre déploiement comprend des serveurs de médiation Microsoft Office Communications Server 2007 R2, ils seront également disponibles dans la liste.

10. Pour associer une ou plusieurs utilisations PSTN à l’itinéraire des communications vocales, cliquez sur **Sélectionner** et choisissez un enregistrement dans la liste des enregistrements d’utilisation PSTN définis pour votre déploiement de Voix Entreprise.
    
    > [!NOTE]  
    > Pour afficher les propriétés de chacun des enregistrements d’utilisation PSTN disponibles, voir <a href="lync-server-2013-view-pstn-usage-records.md">Affichage des enregistrements d’utilisation RTC dans Lync Server 2013</a>.<br />
    Pour créer ou modifier les enregistrements d’utilisation PSTN, voir <a href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Créer une stratégie et voix et configurer les enregistrements d’utilisation PSTN dans Lync Server 2013</a> ou <a href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013</a>.

11. Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour changer la position d’un enregistrement dans la liste, sélectionnez le nom de l’enregistrement, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    > [!NOTE]  
    > Contrairement à une stratégie de voix dans laquelle l’ordre d’apparition des enregistrements d’utilisation PSTN est important, l’ordre des enregistrements d’utilisation PSTN dans un itinéraire des communications vocales n’est pas significatif. Il est toutefois recommandé d’organiser la liste par fréquence d’utilisation, par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Lync Server parcourt la liste du haut vers le bas.)

12. (Facultatif) Tapez une valeur dans le champ **Entrez un numéro traduit à tester** et cliquez sur **OK**. Les résultats du test sont affichés sous le champ.
    
    > [!NOTE]  
    > Vous pouvez enregistrer un itinéraire de communications vocales qui ne réussit pas encore le test, puis le reconfigurer par la suite. Pour plus d’informations, voir <a href="lync-server-2013-test-voice-routing.md">Test du routage des communications vocales dans Lync Server 2013</a>.

13. Cliquez sur **OK**.

14. Dans la page **Itinéraire**, cliquez sur **Valider**, puis sur **Valider tout**.
    
    > [!NOTE]  
    > Chaque fois que vous créez ou modifiez un itinéraire des communications vocales, vous devez exécuter la commande <strong>Valider tout</strong> pour publier la modification de la configuration. Pour plus d’informations, voir <a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</a> dans la documentation des opérations.

## Voir aussi

#### Tâches

[Créer un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md)  
[Affichage des enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Créer une stratégie et voix et configurer les enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### Autres ressources

[Test du routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)

