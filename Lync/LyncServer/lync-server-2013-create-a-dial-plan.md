---
title: 'Lync Server 2013 : Création d’un plan de numérotation'
TOCTitle: Création d’un plan de numérotation
ms:assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398909(v=OCS.15)
ms:contentKeyID: 49298944
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création d’un plan de numérotation dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-10-24_

Pour créer un plan de numérotation, suivez les étapes de la procédure ci-après. Pour modifier un plan de numérotation, reportez-vous à [Modification d’un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

## Pour créer un plan de numérotation

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales** , puis sur **Plan de numérotation** .

4.  Dans la page **Plan de numérotation** , cliquez sur **Nouveau** , puis sélectionnez une étendue pour le plan de numérotation :
    
      - **Plan de numérotation de site** s’applique à tout un site, à l’exception des utilisateurs ou des groupes attribués au plan de numérotation d’un utilisateur. Si vous sélectionnez **Site** comme étendue d’un plan de numérotation, vous devez choisir le site dans la boîte de dialogue **Sélectionner un site** . Si un plan de numérotation a déjà été créé pour un site, le site ne s’affiche pas dans la boîte de dialogue **Sélectionner un site** .
    
      - **Plan de numérotation du pool** peut s’appliquer à une passerelle de réseau téléphonique commuté (RTC) ou à un serveur d’inscriptions. Si vous sélectionnez **Pool** comme étendue d’un plan de numérotation, choisissez la passerelle RTC ou le serveur d’inscriptions dans la boîte de dialogue **Sélectionner un service** . Si un plan de numérotation a déjà été créé pour un service (passerelle RTC ou serveur d’inscriptions), le service ne s’affiche pas dans la liste.
    
      - **Plan de numérotation de l’utilisateur** peut s’appliquer à des utilisateurs ou des groupes spécifiques.
    
    > [!NOTE]  
    > Vous ne pouvez pas modifier l’étendue du plan de numérotation que vous avez sélectionnée.

5.  Si vous créez le plan de numérotation d’un utilisateur, entrez un nom descriptif dans le champ **Nom** de la boîte de dialogue **Nouveau plan de numérotation** . Une fois enregistré, ce nom ne peut pas être modifié.
    
    > [!NOTE]  
    > Pour les plans de numérotation de site, le champ <strong>Nom</strong> contient déjà le nom du site qui ne peut pas être modifié.<br />
    Pour les plans de numérotation du pool, le champ <strong>Nom</strong> contient déjà les noms de la passerelle RTC ou du serveur d’inscriptions qui ne peuvent pas être modifiés.

6.  Le champ **Nom simple** contient déjà le nom qui figure dans le champ **Nom** . Si vous le souhaitez, vous pouvez modifier ce champ pour spécifier un nom qui reflète mieux le site, le service ou l’utilisateur auquel le plan de numérotation s’applique.
    
    > [!IMPORTANT]  
    > Le <strong>nom simple</strong> doit être unique dans l’ensemble des plans de numérotation du déploiement Lync Server. Le nom ne doit pas dépasser 256 caractères Unicode. Sont autorisés les caractères alphabétiques ou numériques, les tirets (-), les points (.) et les traits de soulignement ( _ ).<br />
    Les caractères <strong>non pris en charge</strong> incluent les espaces et les caractères réservés tels que définis dans le standard RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt). Les caractères réservés <strong>non pris en charge</strong> dans le <strong>nom simple</strong> incluent les caractères suivants :<br />
    « ; » « / » « ? » « : » « @ » « &amp; » « = » « + » « $ » « , »

7.  (Facultatif) Dans le champ **Description** , vous pouvez taper des informations descriptives supplémentaires concernant le plan de numérotation.

8.  (Facultatif) Si vous souhaitez utiliser ce plan de numérotation comme une région pour des numéros d’accès entrants, spécifiez une **région de conférence rendez-vous** . Si vous ne souhaitez pas utiliser ce plan de numérotation pour des numéros d’accès entrants, laissez ce champ vide.
    
    > [!NOTE]  
    > Les régions de conférence rendez-vous sont nécessaires pour associer des numéros d’accès entrants à un ou plusieurs plans de numérotation.

9.  (Facultatif) Dans le champ **Préfixe d’accès externe** , entrez une valeur uniquement si les utilisateurs doivent composer un ou plusieurs préfixes supplémentaires (le 0, par exemple) pour obtenir une ligne externe. Vous pouvez taper un préfixe de quatre caractères au maximum (\#, \* et 0-9).
    
    > [!NOTE]  
    > Si vous spécifiez un préfixe d’accès externe, il est inutile de créer une nouvelle règle de normalisation.

10. Associez et configurez les règles de normalisation du plan de numérotation comme suit :
    
      - Pour choisir une ou plusieurs règles dans une liste répertoriant toutes les règles de normalisation disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner** . Dans **Sélectionner des règles de normalisation** , sélectionnez les règles que vous voulez associer au plan de numérotation, puis cliquez sur **OK** .
    
      - Pour définir une nouvelle règle de normalisation et l’associer au plan de numérotation, cliquez sur **Nouveau** . Pour plus d’informations sur la définition d’une nouvelle règle, reportez-vous à [Définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Pour modifier une règle de normalisation déjà associée au plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Afficher les détails** . Pour plus d’informations sur la modification de la règle, reportez-vous à [Définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Pour copier une règle de normalisation existante et l’utiliser comme base de définition d’une nouvelle règle, mettez en surbrillance le nom de la règle, cliquez sur **Copier** , puis sur **Coller** . Pour plus d’informations sur la modification de la copie, reportez-vous à [Définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Pour supprimer une règle de normalisation du plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Supprimer** .
    
    > [!NOTE]  
    > Chaque plan de numérotation doit être associé à au moins une règle de normalisation. Pour savoir comment déterminer les règles de normalisation requises par un plan de numérotation, reportez-vous à <a href="lync-server-2013-dial-plans-and-normalization-rules.md">Plans de numérotation et règles de normalisation dans Lync Server 2013</a> dans la documentation de planification.

11. Vérifiez que les règles de normalisation du plan de numérotation sont classées dans le bon ordre. Pour déplacer une règle dans la liste, sélectionnez-la, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    > [!IMPORTANT]  
    > Lync Server parcourt la liste des règles de normalisation de haut en bas et sélectionne la première règle correspondant au numéro composé. Si vous configurez un plan de numérotation de sorte qu’un numéro composé puisse correspondre à plusieurs règles de normalisation, vérifiez que les règles plus restrictives s’affichent au-dessus des règles moins restrictives.<br />
    La règle de normalisation par défaut <strong>Conserver tout</strong> <strong>^(\d{11})$</strong> fait correspondre tout numéro à 11 chiffres. Par exemple, si vous ajoutez une règle de normalisation qui correspond à des numéros à 11 chiffres commençant par 1425, assurez-vous que la règle de normalisation <strong>Conserver tout</strong> est triée après la règle plus restrictive <strong>^(1425\d{7})$</strong> .

12. (Facultatif) Entrez un numéro pour tester le plan de numérotation, puis cliquez sur **OK** . Les résultats du test s’affichent sous **Numéro composé à tester** .
    
    > [!NOTE]  
    > Vous pouvez enregistrer un plan de numérotation n’ayant pas encore passé le test afin de le reconfigurer ultérieurement. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-test-voice-routing.md">Test du routage des communications vocales dans Lync Server 2013</a>.

13. Cliquez sur **OK** .

14. Dans la page **Plan de numérotation** , cliquez sur **Valider** , puis sur **Valider tout** .
    
    > [!NOTE]  
    > À chaque fois que vous créez un plan de numérotation, vous devez exécuter la commande <strong>Valider tout</strong> pour publier la modification de la configuration. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</a> dans la documentation des opérations.

## Voir aussi

#### Tâches

[Modification d’un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### Autres ressources

[Définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md)

