---
title: 'Lync Server 2013 : Modification d’un plan de numérotation'
TOCTitle: Modification d’un plan de numérotation
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412797(v=OCS.15)
ms:contentKeyID: 49298459
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modification d’un plan de numérotation dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Pour modifier un plan de numérotation existant, suivez les étapes de la procédure ci-après. Pour créer un nouveau plan de numérotation, reportez-vous à [Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

## Pour modifier un plan de numérotation

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales** , puis sur **Plan de numérotation** .

4.  Dans la page **Plan de numérotation** , double-cliquez sur le nom d’un plan de numérotation.
    
    > [!NOTE]  
    > L’étendue et le nom du plan de numérotation ont été définis lors de la création de ce plan. Ils ne peuvent pas être modifiés.

5.  (Facultatif) Dans **Modifier un plan de numérotation** , modifiez le champ **Nom simple** , qui contient déjà le nom qui s’affiche dans le champ **Nom** , pour spécifier un nom qui reflète mieux le site, le service ou l’utilisateur auquel le plan de numérotation s’applique.
    
    > [!IMPORTANT]  
    > Le <strong>nom simple</strong> doit être unique dans tous les plans de numérotation lors du déploiement Lync Server 2013. Il ne doit pas contenir plus de 256 caractères Unicode, chacun pourvant être un caractère alphabétique ou numérique, un tiret (-), un point (.), un signe plus (+) ou un caractère de soulignement (_).<br />
    Les espaces ne sont pas autorisés dans le champ <strong>Nom simple</strong> .

6.  (Facultatif) Dans le champ **Description** , entrez des informations descriptives concernant le plan de numérotation.

7.  (Facultatif) Si vous souhaitez utiliser ce plan de numérotation comme une région pour des numéros d’accès entrants, spécifiez une **région de conférence rendez-vous** . Si vous ne souhaitez pas utiliser ce plan de numérotation pour des numéros d’accès entrants, laissez ce champ vide.
    
    > [!NOTE]  
    > Les régions de conférence rendez-vous sont nécessaires pour associer des numéros d’accès entrants à un ou plusieurs plans de numérotation.

8.  (Facultatif) Dans le champ **Préfixe d’accès externe** , entrez une valeur uniquement si les utilisateurs doivent composer un ou plusieurs préfixes supplémentaires pour obtenir une ligne externe (le 0, par exemple). Vous pouvez taper un préfixe de quatre caractères au maximum (soit \#, \* et 0-9).
    
    > [!NOTE]  
    > Si vous spécifiez un préfixe d’accès externe, il est inutile de créer une nouvelle règle de normalisation.

9.  Associez et configurez les règles de normalisation du plan de numérotation :
    
      - Pour choisir une ou plusieurs règles dans une liste répertoriant toutes les règles de normalisation disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner** . Dans la boîte de dialogue **Sélectionner des règles de normalisation** , sélectionnez les règles que vous voulez associer au plan de numérotation, puis cliquez sur **OK** .
    
      - Pour définir une nouvelle règle de normalisation et l’associer au plan de numérotation, cliquez sur **Nouveau** . Pour plus d’informations sur la définition d’une nouvelle règle, reportez-vous à [Définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Pour modifier une règle de normalisation déjà associée au plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Afficher les détails** . Pour plus d’informations sur la modification de la règle, reportez-vous à [Définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Pour copier une règle de normalisation existante et l’utiliser comme base de définition d’une nouvelle règle, mettez en surbrillance le nom de la règle, cliquez sur **Copier** , puis sur **Coller** . Pour plus d’informations sur la modification de la copie, reportez-vous à [Définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Pour supprimer une règle de normalisation du plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Supprimer** .
    
    > [!NOTE]  
    > Chaque plan de numérotation doit être associé à au moins une règle de normalisation. Pour savoir comment déterminer les règles de normalisation requises par un plan de numérotation, reportez-vous à <a href="lync-server-2013-dial-plans-and-normalization-rules.md">Plans de numérotation et règles de normalisation dans Lync Server 2013</a> dans la documentation de planification.

10. Vérifiez que les règles de normalisation du plan de numérotation sont classées dans le bon ordre. Pour déplacer une règle dans la liste, sélectionnez-la, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    > [!IMPORTANT]  
    > Lync Server parcourt la liste des règles de normalisation de haut en bas et sélectionne la première règle correspondant au numéro composé. Si vous configurez un plan de numérotation de sorte qu’un numéro composé puisse correspondre à plusieurs règles de normalisation, vérifiez que les règles plus restrictives s’affichent au-dessus des règles moins restrictives.<br />
    La règle de normalisation par défaut <strong>Conserver tout</strong> <strong>^(\d{11})$</strong> fait correspondre tout numéro à 11 chiffres. Par exemple, si vous ajoutez une règle de normalisation qui correspond à des numéros à 11 chiffres commençant par 1425, assurez-vous que la règle de normalisation <strong>Conserver tout</strong> est triée après la règle plus restrictive <strong>^(1425\d{7})$</strong> .

11. (Facultatif) Entrez un numéro pour tester le plan de numérotation, puis cliquez sur **OK** . Les résultats du test s’affichent sous **Numéro composé à tester** .
    
    > [!NOTE]  
    > Vous pouvez enregistrer un plan de numérotation n’ayant pas encore passé le test afin de le reconfigurer ultérieurement. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-test-voice-routing.md">Test du routage des communications vocales dans Lync Server 2013</a>.

12. Cliquez sur **OK** .

13. Dans la page **Plan de numérotation** , cliquez sur **Valider** , puis sur **Valider tout** .
    
    > [!NOTE]  
    > Chaque fois que vous créez ou modifiez un plan de numérotation, vous devez exécuter la commande <strong>Valider tout</strong> pour publier la modification de la configuration. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</a> dans la documentation des opérations.

## Voir aussi

#### Tâches

[Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### Autres ressources

[Définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md)

