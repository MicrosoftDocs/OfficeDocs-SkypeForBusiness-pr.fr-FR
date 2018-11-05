---
title: "Exéc. les cas de test du routage des comm. voc. dans Lync Server 2013"
TOCtitle: "Exéc. les cas de test du routage des comm. voc. dans Lync Server 2013"
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg413068(v=OCS.15)
ms:contentKeyID: 49299434
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exécuter les cas de test du routage des communications vocales dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-24_

Vous pouvez exécuter tous les cas de test dans votre suite de cas de test de routage des communications vocales ou vous pouvez exécuter un ou plusieurs cas de test sélectionnés.

## Pour exécuter tous les cas de test de routage des communications vocales

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Tester le routage des communications vocales**.

4.  Sur la page **Tester le routage des com. vocales**, cliquez sur **Action** puis sur **Exécuter tout**.
    
    Le statut de réussite ou d’échec de chaque cas de test apparaît dans la colonne **Réussite/échec**. Si un cas de test n’a pas encore été exécuté, la colonne **Réussite/échec** contient la mention N/A.

5.  (Facultatif) Pour consulter les résultats détaillés de chaque cas de test, double-cliquez sur le nom du cas de test. Les résultats apparaissent dans la zone ombrée sur le côté droit de la page **Modifier le cas de test** :
    
    1.  **Résultat du test** : statut de réussite ou d’échec général pour le test effectué.
    
    2.  **Règle de normalisation** : la première règle de normalisation dans le plan de numérotation sélectionné pour ce cas de test et qui correspond au numéro composé (la valeur dans le champ **Numéro à tester**).
    
    3.  **Numéro normalisé** : la valeur du numéro composé après que la règle de normalisation l’ait traduit.
    
    4.  **Première utilisation PSTN** : l’enregistrement de la première utilisation du réseau téléphonique commuté (PSTN) dans la stratégie de voix sélectionnée pour ce cas de test et qui correspond au numéro composé.
    
    5.  **Premier itinéraire** : le premier itinéraire des communications vocales dans l’enregistrement de la première utilisation PSTN qui correspond au numéro composé.
        
        > [!NOTE]  
        > Les champs <strong>Enregistrement d’utilisation PSTN attendu</strong> et <strong>Itinéraire attendu</strong> sont facultatifs dans la configuration d’un cas de test de routage des communications vocales. Si les cas de test ne spécifient pas ces valeurs, le champ correspondant dans les résultats de test sera vide.

## Pour exécuter un ou plusieurs cas de test de routage des communications vocales

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Tester le routage des communications vocales**.

4.  Sur la page **Tester le routage des com. vocales**, cliquez sur le nom des cas de test que vous souhaitez exécuter.

5.  Dans le menu **Action**, cliquez sur **Exécuter la sélection**.
    
    Le statut de réussite ou d’échec de chaque cas de test apparaît dans la colonne **Réussite/échec**. Si un cas de test n’a pas encore été exécuté, la colonne **Réussite/échec** contient la mention N/A.

6.  (Facultatif) Pour consulter les résultats détaillés de chaque cas de test, double-cliquez sur le nom du cas de test. Les résultats apparaissent dans la zone ombrée sur le côté droit de la page **Modifier le cas de test** :
    
    1.  **Résultat du test** : statut de réussite ou d’échec général pour le test effectué.
    
    2.  **Règle de normalisation** : la première règle de normalisation dans le plan de numérotation sélectionné pour ce cas de test et qui correspond au numéro composé (la valeur dans le champ **Numéro à tester**).
    
    3.  **Numéro normalisé** : la valeur du numéro composé après que la règle de normalisation l’ait traduit.
    
    4.  **Première utilisation PSTN** : l’enregistrement de la première utilisation PSTN dans la stratégie de voix sélectionnée pour ce cas de test et qui correspond au numéro composé.
    
    5.  **Premier itinéraire** : le premier itinéraire des communications vocales dans l’enregistrement de la première utilisation PSTN qui correspond au numéro composé.
        
        > [!NOTE]  
        > Les champs <strong>Enregistrement d’utilisation PSTN attendu</strong> et <strong>Itinéraire attendu</strong> sont facultatifs dans la configuration d’un cas de test de routage des communications vocales. Si les cas de test ne spécifient pas ces valeurs, le champ correspondant dans les résultats de test sera vide.

## Voir aussi

#### Autres ressources

[Test du routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)  
[Exécution des tests de routage des communications vocales dans Lync Server 2013](lync-server-2013-running-voice-routing-tests.md)

