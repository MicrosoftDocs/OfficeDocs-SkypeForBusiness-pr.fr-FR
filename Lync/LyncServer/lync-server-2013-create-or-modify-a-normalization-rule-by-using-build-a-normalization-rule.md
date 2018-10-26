---
title: "LS 2013 : Créa. ou mod. d’une règle de norm. avec la section du même nom"
TOCTitle: Création ou modification d’une règle de normalisation avec la section Création d’une règle de normalisation
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg399036(v=OCS.15)
ms:contentKeyID: 49299190
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification d’une règle de normalisation avec la section Création d’une règle de normalisation dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Effectuez les étapes suivantes si vous souhaitez créer ou modifier une règle de normalisation dans le Panneau de configuration Lync Server. Si vous souhaitez créer ou modifier manuellement une règle de normalisation, reportez-vous à [Création ou modification manuelle d’une règle de normalisation dans Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md) (contenu éventuellement en anglais).

## Pour définir une règle à l’aide de la section Créer une règle de normalisation

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  (Optionnel) Suivez les étapes de la section [Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md) jusqu’à l’étape 11 ou de la section [Modification d’un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) (contenus éventuellement en anglais) jusqu’à l’étape 10.

4.  Dans la section **Nouvelle règle de normalisation** ou **Modifier une règle de normalisation** , entrez un nom décrivant le modèle de numéro en cours de normalisation dans le champ **Nom** (par exemple, **Postes5chiffres** ).

5.  (Optionnel) Dans **Description** , entrez une description de la règle de normalisation (par exemple, « Traduit les postes à 5 chiffres »).

6.  Dans **Créer une règle de normalisation** , entrez les valeurs dans les champs suivants :
    
      - **Chiffres de début**    (Optionnel) Spécifiez les chiffres de début des numéros composés que le modèle doit suivre. Par exemple, tapez **425** si vous souhaitez que le modèle suive les numéros composés commençant par 425.
    
      - **Longueur**    Spécifiez le nombre de chiffres du modèle à suivre et indiquez si vous souhaitez que le modèle suive exactement cette longueur, les numéros composés affichant au moins cette longueur ou les numéros composés quelle que soit leur longueur.
    
      - **Chiffres à supprimer**    (Optionnel) Spécifiez le nombre de chiffres de début à supprimer des numéros composés que le modèle doit suivre.
    
      - **Chiffres à ajouter**    (Optionnel) Spécifiez les chiffres à ajouter aux numéros composés que le modèle doit suivre.
    
    Les valeurs que vous entrez dans ces champs s’affichent dans **Modèle à suivre** et **Règle de conversion** . Par exemple, si vous laissez vide le champ **Chiffres de début** , tapez **7** dans le champ **Longueur** et sélectionnez **Exactement** , puis spécifiez **0** dans le champ **Chiffres à supprimer** , l’expression régulière obtenue dans **Modèle à suivre** est :
    
    **^(\\d{7})$**

7.  Dans **Règle de conversion** , spécifiez comme suit le modèle du format des numéros de téléphone E.164 convertis :
    
      - Une valeur qui représente le nombre de chiffres spécifiés dans le modèle à suivre. Par exemple, si le modèle à suivre est **^(\\d{7})$** , alors la valeur **$1** de la règle de conversion représente des numéros composés à 7 chiffres.
    
      - (Optionnel) Entrez une valeur dans le champ **Chiffres à ajouter** pour spécifier les chiffres à ajouter au numéro converti (par exemple, **+1425** ).
    
    Par exemple, si **Modèle à suivre** contient **^(\\d{7})$** comme modèle des numéros composés et **Règle de conversion** contient **+1425$1** comme modèle des numéros de téléphone E.164, la règle normalise 5550100 à la valeur +14255550100.

8.  (Optionnel) Si la règle de normalisation est convertie en un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne** .

9.  (Optionnel) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK** . Les résultats du test s’affichent sous **Numéro composé à tester** .
    
    > [!NOTE]  
    > Vous pouvez enregistrer une règle de normalisation n’ayant pas encore passé le test afin de la reconfigurer ultérieurement. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-test-voice-routing.md">Test du routage des communications vocales dans Lync Server 2013</a>.

10. Cliquez sur **OK** pour enregistrer la règle de normalisation.

11. Cliquez sur **OK** pour enregistrer le plan de numérotation.

12. Dans la page **Plan de numérotation** , cliquez sur **Valider** , puis sur **Valider tout** .
    
    > [!NOTE]  
    > Lorsque vous créez ou modifiez une règle de normalisation, vous devez exécuter la commande <strong>Valider tout</strong> pour publier la modification de configuration. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</a> dans la documentation des opérations.

## Voir aussi

#### Tâches

[Création ou modification manuelle d’une règle de normalisation dans Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modification d’un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### Autres ressources

[Test du routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)

