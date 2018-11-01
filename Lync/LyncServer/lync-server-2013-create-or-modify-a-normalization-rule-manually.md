---
title: "Lync Server 2013 : Créa. ou modification manuelle d’une règle de normalisation"
TOCTitle: Création ou modification manuelle d’une règle de normalisation
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg413074(v=OCS.15)
ms:contentKeyID: 49299431
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification manuelle d’une règle de normalisation dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-22_

Suivez cette procédure si vous souhaitez créer ou modifier manuellement une règle de normalisation. Si vous souhaitez créer ou modifier une règle de normalisation à l’aide de l’outil Créer une règle de normalisation dans le Panneau de configuration Lync Server, reportez-vous à [Création ou modification d’une règle de normalisation avec la section Création d’une règle de normalisation dans Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).

## Pour définir une règle de normalisation manuellement

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  (Facultatif) Suivez la procédure décrite dans [Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md) ou [Modification d’un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

4.  Dans **Nouvelle règle de normalisation** ou **Modifier une règle de normalisation**, entrez un nom qui décrive le modèle de numéro à normaliser dans **Nom** (par exemple, nommez la règle de normalisation **Poste5chiffres** ).

5.  (Facultatif) Dans le champ **Description**, entrez la description de la règle de normalisation, par exemple, « Traduit les numéros de poste à 5 chiffres ».

6.  Dans **Créer une règle de normalisation**, cliquez sur **Modifier**.

7.  Entrez ce qui suit dans **Taper une expression régulière**  :
    
      - Dans **Suivre ce modèle**, indiquez le modèle que vous souhaitez utiliser pour le numéro de téléphone composé.
    
      - Dans **Règle de conversion**, précisez un modèle pour le format des numéros de téléphone E.164 convertis.
    
    Par exemple, si vous entrez **^(\\d{7})$** dans le champ **Suivre ce modèle** et **+1425$1** dans le champ **Règle de conversion**, la règle normalisera le numéro 5550100 comme suit, +14255550100.

8.  (Optionnel) Si la règle de normalisation est convertie en un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne**.

9.  (Optionnel) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK**. Les résultats du test s’affichent sous **Numéro composé à tester**.
    
    > [!NOTE]  
    > Vous pouvez enregistrer une règle de normalisation n’ayant pas encore passé le test afin de la reconfigurer ultérieurement. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-test-voice-routing.md">Test du routage des communications vocales dans Lync Server 2013</a>.

10. Cliquez sur **OK** pour enregistrer la règle de normalisation.

11. Cliquez sur **OK** pour enregistrer le plan de numérotation.

12. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.
    
    > [!NOTE]  
    > Lorsque vous créez ou modifiez une règle de normalisation, vous devez exécuter la commande <strong>Valider tout</strong> pour publier la modification de configuration. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</a> dans la documentation des opérations.

## Voir aussi

#### Tâches

[Création ou modification d’une règle de normalisation avec la section Création d’une règle de normalisation dans Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modification d’un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### Autres ressources

[Test du routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)

