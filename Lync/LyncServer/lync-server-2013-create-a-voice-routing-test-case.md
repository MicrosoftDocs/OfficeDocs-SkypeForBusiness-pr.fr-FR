---
title: "Lync Server 2013 : Créa. d’un cas de test de routage des comm. vocales"
TOCTitle: Création d’un cas de test de routage des communications vocales
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425935(v=OCS.15)
ms:contentKeyID: 49297043
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création d’un cas de test de routage des communications vocales dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-02-07_

## Pour créer un cas de test

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Tester le routage des communications vocales**.

4.  Dans la page **Routage des communications vocales**, cliquez sur **Nouveau** pour créer un nouveau cas de test.

5.  Dans **Nom**, tapez un nom unique pour le cas de test.
    
    Le nom doit être unique parmi tous les cas de test de routage des communications vocales dans votre déploiement Voix Entreprise. Il peut comporter jusqu’à 32 caractères et contenir n’importe quel caractère alphanumérique en plus de la barre oblique inverse (\\), du point (.) ou du trait de soulignement (\_).

6.  Dans **Numéro composé à tester**, tapez le numéro composé que vous souhaitez utiliser pour tester la configuration du routage que vous spécifiez pour ce cas de test. À partir du plan de numérotation, de l’itinéraire et de la stratégie de voix, ce numéro sera normalisé et affiché en sortie.

7.  Dans la liste **Plan de numérotation**, sélectionnez le plan de numérotation à utiliser lors de l’exécution du test. Le plan de numérotation global est utilisé par défaut.

8.  Dans la liste **Stratégie de la voix**, sélectionnez la stratégie de voix à utiliser lors de l’exécution du test. La stratégie de voix globale est utilisée par défaut.

9.  Dans **Conversion attendue**, tapez le numéro de téléphone au format dans lequel vous souhaitez le visualiser après la conversion. Il s’agit de la valeur du numéro de téléphone que vous testez une fois qu’il a été converti par la première règle de normalisation qui correspond dans le plan de numérotation sélectionné. Quand vous exécutez le cas de test, si le numéro que vous testez ne correspond pas à la valeur contenue dans **Conversion attendue** le test échoue.

10. (Facultatif) Dans la liste **Utilisation RTC attendue**, vous pouvez sélectionner l’enregistrement d’utilisation RTC devant être utilisé quand vous exécutez le cas de test, en fonction de la stratégie de voix et du plan de numérotation spécifiés. Si un autre enregistrement d’utilisation RTC est utilisé, le test échoue.

11. (Facultatif) Dans la liste **Itinéraire attendu**, vous pouvez sélectionner l’itinéraire des communications vocales devant être utilisé lorsque vous exécutez le cas de test, en fonction de la stratégie de voix et du plan de numérotation spécifiés. Si un autre itinéraire des communications vocales est utilisé, le test échoue.

12. (Facultatif) Cliquez sur **Exécuter** pour exécuter le cas de test. Les résultats s’affichent dans le panneau droit de la page.

13. Cliquez sur **OK**.

14. Cliquez sur **Valider**, puis sur **Valider tout**.
    
    > [!NOTE]  
    > Chaque fois que vous créez un cas de test de routage des communications vocales, vous devez exécuter la commande <strong>Valider tout</strong> pour publier la modification de la configuration. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</a> dans la documentation des opérations.    
    
    
    Si le plan de numérotation utilisé dans le test normalise les numéros de téléphone commençant par un signe plus (par exemple, +12065551219), ce plan peut entraîner l’échec du test de routage des communications vocales. (Le plan de numérotation et le routage des communications vacales fonctionneront ; en fait, Test-CsDialPlan réussira. Cependant, le test de routage des communications vocales risque d’échouer.) Il convient de ne pas perdre de vue cela lors des tests du routage des communications vocales.

## Voir aussi

#### Tâches

[Exportation des cas de test de routage des communications vocales dans Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
[Importation des cas de test de routage des communications vocales dans Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  

#### Autres ressources

[Configuration des plans de numérotation dans Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Configuration des stratégies de voix, des enregistrements d’utilisation du RTC et des itinéraires des communications vocales dans Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

