---
title: 'Lync Server 2013 : modifier un plan de numérotation'
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
ms.openlocfilehash: f2c4f922565b5b3af5613de4a5e43c79cf573410
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-a-dial-plan-in-lync-server-2013"></a>Modifier un plan de numérotation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Pour modifier un plan de numérotation existant, suivez les étapes de la procédure ci-après. Si vous souhaitez créer un nouveau plan de numérotation, voir [créer un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

<div>

## <a name="to-modify-a-dial-plan"></a>Pour modifier un plan de numérotation

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Plan de numérotation**.

4.  Dans la page **Plan de numérotation**, double-cliquez sur le nom d’un plan de numérotation.
    
    <div>
    

    > [!NOTE]  
    > L’étendue et le nom du plan de numérotation ont été définis lors de la création de ce plan. Ils ne peuvent pas être modifiés.

    
    </div>

5.  (Facultatif) Dans **Modifier un plan de numérotation**, modifiez le champ **Nom simple**, qui contient déjà le nom qui apparaît dans le champ **Nom**, pour spécifier un nom qui reflète mieux le site, le service ou l’utilisateur auquel le plan de numérotation s’applique.
    
    <div>
    

    > [!IMPORTANT]  
    > Le <STRONG>nom simple</STRONG> doit être unique parmi tous les plans de numérotation dans le déploiement Lync Server 2013. Il ne peut pas dépasser 256 caractères Unicode, chacun pouvant être un caractère alphabétique ou numérique, un tiret (-), un point (.), un signe plus (+) ou un trait de soulignement (_).<BR>Les espaces ne sont pas autorisés dans le champ <STRONG>Nom simple</STRONG>.

    
    </div>

6.  (Facultatif) Dans le champ **Description**, entrez des informations descriptives concernant le plan de numérotation.

7.  (Facultatif) Si vous souhaitez utiliser ce plan de numérotation comme une région pour des numéros d’accès entrants, spécifiez une **région de conférence rendez-vous**. Si vous ne souhaitez pas utiliser ce plan de numérotation pour des numéros d’accès entrants, laissez ce champ vide.
    
    <div>
    

    > [!NOTE]  
    > Les régions de conférence rendez-vous sont nécessaires pour associer des numéros d’accès entrants à un ou plusieurs plans de numérotation.

    
    </div>

8.  (Facultatif) Dans le champ **Préfixe d’accès externe**, entrez une valeur uniquement si les utilisateurs doivent composer un ou plusieurs préfixes supplémentaires pour obtenir une ligne externe (le 0, par exemple). Vous pouvez taper une valeur de préfixe pouvant comporter jusqu’à quatre caractères ( \# \*c’est-à-dire,, et 0-9).
    
    <div>
    

    > [!NOTE]  
    > Si vous spécifiez un préfixe d’accès externe, il est inutile de créer une nouvelle règle de normalisation.

    
    </div>

9.  Associez et configurez les règles de normalisation du plan de numérotation :
    
      - Pour choisir une ou plusieurs règles dans la liste de toutes les règles de normalisation disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Dans la boîte de dialogue **Sélectionner des règles de normalisation**, sélectionnez les règles que vous voulez associer au plan de numérotation, puis cliquez sur **OK**.
    
      - Pour définir une nouvelle règle de normalisation et l’associer au plan de numérotation, cliquez sur **Nouveau**. Pour plus d’informations sur la définition d’une nouvelle règle, reportez-vous à la rubrique [définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Pour modifier une règle de normalisation déjà associée au plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Afficher les détails**. Pour plus d’informations sur la modification de la règle, reportez-vous à la rubrique [définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Pour copier une règle de normalisation existante et l’utiliser comme base de définition d’une nouvelle règle, mettez en surbrillance le nom de la règle, cliquez sur **Copier**, puis sur **Coller**. Pour plus d’informations sur la modification de la copie, reportez-vous à la rubrique [définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Pour supprimer une règle de normalisation du plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Supprimer**.
    
    <div>
    

    > [!NOTE]  
    > Chaque plan de numérotation doit être associé à au moins une règle de normalisation. Pour plus d’informations sur la façon de déterminer toutes les règles de normalisation requises par un plan de numérotation, voir <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and Normalization Rules in Lync Server 2013</A> dans la documentation de planification.

    
    </div>

10. Vérifiez que les règles de normalisation du plan de numérotation sont classées dans le bon ordre. Pour déplacer une règle dans la liste, sélectionnez-la, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server parcourt la liste des règles de normalisation du haut vers le bas et utilise la première règle qui correspond au numéro composé. Si vous configurez un plan de numérotation de sorte qu’un numéro composé puisse correspondre à plusieurs règles de normalisation, vérifiez que les règles plus restrictives apparaissent au-dessus des règles moins restrictives.<BR>La règle de normalisation <STRONG>conserver toutes les</STRONG> règles de normalisation <STRONG>{11}^ (\d) $</STRONG> correspond à n’importe quel numéro à 11 chiffres. Si, par exemple, vous ajoutez une règle de normalisation qui correspond à des numéros à 11 chiffres commençant par 1425, assurez-vous que la règle <STRONG>conserver tout</STRONG> est triée en dessous de la règle <STRONG>^ (1425 \{7}d) $</STRONG> plus restrictive.

    
    </div>

11. (Facultatif) Entrez un numéro pour tester le plan de numérotation, puis cliquez sur **OK**. Les résultats du test apparaissent sous **Numéro composé à tester**.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez enregistrer un plan de numérotation n’ayant pas encore passé le test afin de le reconfigurer ultérieurement. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-test-voice-routing.md">test de routage des communications vocales dans Lync Server 2013</A>.

    
    </div>

12. Cliquez sur **OK**.

13. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.
    
    <div>
    

    > [!NOTE]  
    > Chaque fois que vous créez ou modifiez un plan de numérotation, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de la configuration. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Publier les modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

