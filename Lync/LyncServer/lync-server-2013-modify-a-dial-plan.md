---
title: 'Lync Server 2013 : Modification d’un plan de numérotation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a dial plan
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412797(v=OCS.15)
ms:contentKeyID: 48185099
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd4c007933eb7186e412ada1a3f4c35b241f5eff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-dial-plan-in-lync-server-2013"></a>Modification d’un plan de numérotation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Pour modifier un plan de numérotation existant, suivez les étapes de la procédure ci-dessous. Pour créer un nouveau plan de numérotation, reportez-vous à [la rubrique créer un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

<div>

## <a name="to-modify-a-dial-plan"></a>Pour modifier un plan de numérotation

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Plan de numérotation**.

4.  Dans la page **Plan de numérotation**, double-cliquez sur le nom d’un plan de numérotation.
    
    <div>
    

    > [!NOTE]  
    > L’étendue et le nom du plan de numérotation ont été définis lors de la création de ce plan. Ils ne peuvent pas être modifiés.

    
    </div>

5.  (Facultatif) Dans **Modifier un plan de numérotation**, modifiez le champ **Nom simple**, qui contient déjà le nom qui s’affiche dans le champ **Nom**, pour spécifier un nom qui reflète mieux le site, le service ou l’utilisateur auquel le plan de numérotation s’applique.
    
    <div>
    

    > [!IMPORTANT]  
    > Le <STRONG>nom simple</STRONG> doit être unique parmi tous les plans de numérotation dans le déploiement de Lync Server 2013. Il ne doit pas contenir plus de 256 caractères Unicode, chacun pouvant être un caractère alphabétique ou numérique, un tiret (-), un point (.), un signe plus (+) ou un caractère de soulignement (_).<BR>Les espaces ne sont pas autorisés dans le champ <STRONG>Nom simple</STRONG>.

    
    </div>

6.  (Facultatif) Dans le champ **Description**, entrez des informations descriptives concernant le plan de numérotation.

7.  (Facultatif) Si vous souhaitez utiliser ce plan de numérotation comme une région pour des numéros d’accès entrants, spécifiez une **région de conférence rendez-vous**. Si vous ne souhaitez pas utiliser ce plan de numérotation pour des numéros d’accès entrants, laissez ce champ vide.
    
    <div>
    

    > [!NOTE]  
    > Les régions de conférence rendez-vous sont nécessaires pour associer des numéros d’accès entrants à un ou plusieurs plans de numérotation.

    
    </div>

8.  (Facultatif) Dans le champ **Préfixe d’accès externe**, entrez une valeur uniquement si les utilisateurs doivent composer un ou plusieurs préfixes supplémentaires pour obtenir une ligne externe (le 9, par exemple). Vous pouvez taper une valeur de préfixe composée de quatre caractères au maximum (c’est-à-dire \#, \*et 0-9).
    
    <div>
    

    > [!NOTE]  
    > Si vous spécifiez un préfixe d’accès externe, il est inutile de créer une nouvelle règle de normalisation.

    
    </div>

9.  Associez et configurez les règles de normalisation du plan de numérotation :
    
      - Pour sélectionner une ou plusieurs règles dans la liste de toutes les règles de normalisation disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Dans la boîte de dialogue **Sélectionner des règles de normalisation**, sélectionnez les règles que vous voulez associer au plan de numérotation, puis cliquez sur **OK**.
    
      - Pour définir une nouvelle règle de normalisation et l’associer au plan de numérotation, cliquez sur **Nouveau**. Pour plus d’informations sur la définition d’une règle, voir [définition des règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Pour modifier une règle de normalisation déjà associée au plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Afficher les détails**. Pour plus d’informations sur la modification de la règle, voir [définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Pour copier une règle de normalisation existante et l’utiliser comme base de définition d’une nouvelle règle, mettez en surbrillance le nom de la règle, cliquez sur **Copier**, puis sur **Coller**. Pour plus d’informations sur la modification de la copie, voir [définir les règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Pour supprimer une règle de normalisation du plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Supprimer**.
    
    <div>
    

    > [!NOTE]  
    > Chaque plan de numérotation doit être associé à au moins une règle de normalisation. Pour plus d’informations sur la façon de déterminer toutes les règles de normalisation requises par un plan de numérotation, reportez-vous à la rubrique <A href="lync-server-2013-dial-plans-and-normalization-rules.md">plans de numérotation et règles de normalisation dans Lync Server 2013</A> dans la documentation de planification.

    
    </div>

10. Vérifiez que les règles de normalisation du plan de numérotation sont classées dans le bon ordre. Pour déplacer une règle dans la liste, sélectionnez-la, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server parcourt la liste des règles de normalisation du haut vers le bas et utilise la première règle qui correspond au numéro numéroté. Si vous configurez un plan de numérotation de sorte qu’un numéro composé puisse correspondre à plusieurs règles de normalisation, vérifiez que les règles plus restrictives s’affichent au-dessus des règles moins restrictives.<BR><STRONG>Par défaut</STRONG> , la règle de normalisation <STRONG>^ (\d{11}) $</STRONG> correspond à n’importe quel numéro à 11 chiffres. Par exemple, si vous ajoutez une règle de normalisation qui correspond à des numéros à 11 chiffres commençant par 1425, assurez-vous que la valeur <STRONG>conserver tout</STRONG> est triée sous la règle plus restrictive <STRONG>^ (1425 \{7}d) $</STRONG> .

    
    </div>

11. (Facultatif) Entrez un numéro pour tester le plan de numérotation, puis cliquez sur **OK**. Les résultats du test s’affichent sous **Numéro composé à tester**.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez enregistrer un plan de numérotation n’ayant pas encore passé le test afin de le reconfigurer ultérieurement. Pour plus d’informations, consultez <A href="lync-server-2013-test-voice-routing.md">tester le routage vocal dans Lync Server 2013</A>.

    
    </div>

12. Cliquez sur **OK**.

13. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.
    
    <div>
    

    > [!NOTE]  
    > Chaque fois que vous créez ou modifiez un plan de numérotation, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de la configuration. Pour plus d’informations, reportez-vous <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">à la rubrique publier des modifications en attente sur la configuration de l’acheminement de la voix dans Lync Server 2013</A> dans la documentation

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Créer un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Publier les modifications en attente apportées à la configuration du routage de la voix dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

