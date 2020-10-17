---
title: 'Lync Server 2013 : création d’un plan de numérotation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a dial plan
ms:assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398909(v=OCS.15)
ms:contentKeyID: 48185424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f530faa83cb2e924d93abce6f7496c3ef1b82311
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516921"
---
# <a name="create-a-dial-plan-in-lync-server-2013"></a>Création d’un plan de numérotation dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-24_

Pour créer un plan de numérotation, suivez les étapes de la procédure ci-après. Pour modifier un plan de numérotation, reportez-vous à la rubrique [modifier un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

<div>

## <a name="to-create-a-dial-plan"></a>Pour créer un plan de numérotation

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Plan de numérotation**.

4.  Dans la page **Plan de numérotation**, cliquez sur **Nouveau**, puis sélectionnez une étendue pour le plan de numérotation :
    
      - **Plan de numérotation de site** s’applique à tout un site, à l’exception des utilisateurs ou des groupes qui sont attribués au plan de numérotation d’un utilisateur. Si vous sélectionnez **Site** comme étendue d’un plan de numérotation, vous devez choisir le site dans la boîte de dialogue **Sélectionner un site**. Si un plan de numérotation a déjà été créé pour un site, le site n’apparaît pas dans la boîte de dialogue **Sélectionner un site**.
    
      - **Plan de numérotation du pool** peut s’appliquer à une passerelle de réseau téléphonique commuté (PSTN) ou à un serveur d’inscriptions. Si vous sélectionnez **Pool** comme étendue d’un plan de numérotation, choisissez la passerelle PSTN ou le serveur d’inscriptions dans la boîte de dialogue **Sélectionner un service**. Si un plan de numérotation a déjà été créé pour un service (passerelle PSTN ou serveur d’inscriptions), le service n’apparaît pas dans la liste.
    
      - **Plan de numérotation de l’utilisateur** peut s’appliquer à des utilisateurs ou des groupes spécifiques.
    
    <div>
    

    > [!NOTE]  
    > Vous ne pouvez pas modifier l’étendue du plan de numérotation que vous avez sélectionnée.

    
    </div>

5.  Si vous créez le plan de numérotation d’un utilisateur, entrez un nom descriptif dans le champ **Nom** de la boîte de dialogue **Nouveau plan de numérotation**. Une fois enregistré, ce nom ne peut pas être modifié.
    
    <div>
    

    > [!NOTE]  
    > Pour les plans de numérotation de site, le champ <STRONG>Nom</STRONG> contient déjà le nom du site qui ne peut pas être modifié.<BR>Pour les plans de numérotation du pool, le champ <STRONG>Nom</STRONG> contient déjà les noms de la passerelle PSTN ou du serveur d’inscriptions qui ne peuvent pas être modifiés.

    
    </div>

6.  Le champ **Nom simple** contient déjà le nom qui figure dans le champ **Nom**. Si vous le souhaitez, vous pouvez modifier ce champ pour spécifier un nom qui reflète mieux le site, le service ou l’utilisateur auquel le plan de numérotation s’applique.
    
    <div>
    

    > [!IMPORTANT]  
    > Le <STRONG>nom simple</STRONG> doit être unique parmi tous les plans de numérotation dans le déploiement Lync Server. Il ne peut pas dépasser 256 caractères Unicode, chacun pouvant être un caractère alphabétique ou numérique, un tiret (-), un point (.) ou un trait de soulignement (_).<BR>Les caractères <STRONG>non pris en charge</STRONG> incluent les espaces et les caractères réservés tels que définis dans le document RFC 3966 ( http://www.ietf.org/rfc/rfc3966.txt) . Les caractères réservés qui <STRONG>ne sont pas pris en charge</STRONG> dans le <STRONG>nom simple</STRONG> sont les suivants :<BR>";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","

    
    </div>

7.  (Facultatif) Dans le champ **Description**, vous pouvez taper des informations descriptives supplémentaires concernant le plan de numérotation.

8.  (Facultatif) Si vous souhaitez utiliser ce plan de numérotation comme une région pour des numéros d’accès entrants, spécifiez une **région de conférence rendez-vous**. Si vous ne souhaitez pas utiliser ce plan de numérotation pour des numéros d’accès entrants, laissez ce champ vide.
    
    <div>
    

    > [!NOTE]  
    > Les régions de conférence rendez-vous sont nécessaires pour associer des numéros d’accès entrants à un ou plusieurs plans de numérotation.

    
    </div>

9.  (Facultatif) Dans le champ **Préfixe d’accès externe**, entrez une valeur uniquement si les utilisateurs doivent composer un ou plusieurs préfixes supplémentaires (le 0, par exemple) pour obtenir une ligne externe. Vous pouvez taper une valeur de préfixe de quatre caractères ( \# ,, \* et 0-9).
    
    <div>
    

    > [!NOTE]  
    > Si vous spécifiez un préfixe d’accès externe, il est inutile de créer une nouvelle règle de normalisation.

    
    </div>

10. Associez et configurez les règles de normalisation du plan de numérotation comme suit :
    
      - Pour choisir une ou plusieurs règles dans la liste de toutes les règles de normalisation disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Dans **Sélectionner des règles de normalisation**, sélectionnez les règles que vous voulez associer au plan de numérotation, puis cliquez sur **OK**.
    
      - Pour définir une nouvelle règle de normalisation et l’associer au plan de numérotation, cliquez sur **Nouveau**. Pour plus d’informations sur la définition d’une nouvelle règle, reportez-vous à la rubrique [définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Pour modifier une règle de normalisation déjà associée au plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Afficher les détails**. Pour plus d’informations sur la modification de la règle, reportez-vous à la rubrique [définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Pour copier une règle de normalisation existante et l’utiliser comme base de définition d’une nouvelle règle, mettez en surbrillance le nom de la règle, cliquez sur **Copier**, puis sur **Coller**. Pour plus d’informations sur la modification de la copie, reportez-vous à la rubrique [définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Pour supprimer une règle de normalisation du plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Supprimer**.
    
    <div>
    

    > [!NOTE]  
    > Chaque plan de numérotation doit être associé à au moins une règle de normalisation. Pour plus d’informations sur la façon de déterminer toutes les règles de normalisation requises par un plan de numérotation, voir <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and Normalization Rules in Lync Server 2013</A> dans la documentation de planification.

    
    </div>

11. Vérifiez que les règles de normalisation du plan de numérotation sont classées dans le bon ordre. Pour déplacer une règle dans la liste, sélectionnez-la, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server parcourt la liste des règles de normalisation du haut vers le bas et utilise la première règle qui correspond au numéro composé. Si vous configurez un plan de numérotation de sorte qu’un numéro composé puisse correspondre à plusieurs règles de normalisation, vérifiez que les règles plus restrictives apparaissent au-dessus des règles moins restrictives.<BR>La règle de normalisation <STRONG>conserver toutes les</STRONG> règles de normalisation <STRONG>^ (\d {11} ) $</STRONG> correspond à n’importe quel numéro à 11 chiffres. Par exemple, si vous ajoutez une règle de normalisation qui correspond à des numéros à 11 chiffres commençant par 1425, assurez-vous que la règle <STRONG>conserver tout</STRONG> est triée en dessous de la règle <STRONG>^ (1425 \ d {7} ) $</STRONG> plus restrictive.

    
    </div>

12. (Facultatif) Entrez un numéro pour tester le plan de numérotation, puis cliquez sur **OK**. Les résultats du test apparaissent sous **Numéro composé à tester**.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez enregistrer un plan de numérotation n’ayant pas encore passé le test afin de le reconfigurer ultérieurement. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-test-voice-routing.md">test de routage des communications vocales dans Lync Server 2013</A>.

    
    </div>

13. Cliquez sur **OK**.

14. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.
    
    <div>
    

    > [!NOTE]  
    > À chaque fois que vous créez un plan de numérotation, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de la configuration. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Modifier un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Publier les modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

