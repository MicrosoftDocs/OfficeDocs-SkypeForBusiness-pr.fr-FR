---
title: 'Lync Server 2013 : Configuration du proxy inverse pour la mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the reverse proxy for mobility
ms:assetid: 3f4a9e33-77e4-4c18-a73f-24d4bec8ea9c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690011(v=OCS.15)
ms:contentKeyID: 48183946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 657ddf0711b0a14c9ce861a0f237977c9a2369c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-reverse-proxy-for-mobility-in-lync-server-2013"></a>Configuration du proxy inverse pour la mobilité dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-03-20_

Si vous souhaitez utiliser la découverte automatique pour les clients d’appareils mobiles, vous devez modifier ou créer une nouvelle règle de publication Web pour le proxy inverse, que vous ayez ou non mis à jour les listes de noms de remplacement de l’objet sur les certificats proxy inverse.

Si vous décidez d’utiliser HTTPs pour les demandes de service de découverte automatique Lync Server 2013 et de mettre à jour les listes de noms de remplacement d’objet sur les certificats de proxy inverse, vous devez affecter le certificat public mis à jour à l’écouteur SSL (Secure Sockets Layer) sur votre proxy inverse. Pour plus d’informations sur les entrées de nom de remplacement d’objet requises, voir [configuration technique requise pour la mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). Vous devez ensuite modifier l’écouteur existant pour les services Web externes ou créer une nouvelle règle de publication Web pour l’URL du service de découverte automatique externe. Si vous ne disposez pas encore d’une règle de publication sur le Web pour l’URL des services Web Lync Server 2013 externes pour votre pool frontal, vous devez également publier une règle pour celle-ci.

<div>


> [!NOTE]  
> La règle de publication de proxy inverse et l’écouteur peuvent service à la fois les services Web externes et le service de découverte automatique, tant que le certificat attribué à l’écouteur contient le nom du sujet et les noms de remplacement de l’objet requis pour les deux. Pour plus d’informations sur la configuration par défaut de l’écouteur et de la règle de publication sur le Web, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">configuration de serveurs proxy inverse pour Lync Server 2013</A> pour plus d’informations.



</div>

Si vous décidez d’utiliser HTTP pour les demandes de service de découverte automatique initiales afin de ne pas avoir besoin de mettre à jour les autres noms d’objet du proxy inverse, vous devez créer ou modifier une règle de publication Web pour le port 80.

Les procédures décrites dans cette section expliquent comment créer ou modifier les règles de publication Web dans Microsoft Forefront Threat Management Gateway 2010 pour la découverte automatique.

<div>


> [!NOTE]  
> Les procédures suivantes présupposent que vous avez installé l’édition standard de Forefront Threat Management Gateway (TMG) 2010. Si vous utilisez un autre proxy inverse, les procédures sont similaires, mais doivent être mappées à la documentation du produit tiers.



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Pour créer une règle de publication Web pour l’URL de découverte automatique externe

1.  Cliquez sur **Démarrer**, pointez sur **programmes**, sur **Microsoft Forefront TMG**, puis cliquez sur gestion de **Forefront TMG**.

2.  Dans le volet gauche, développez **NomServeur**, cliquez avec le bouton droit sur **stratégie de pare-feu**, pointez sur **nouveau**, puis cliquez sur règle de **publication de site Web**.

3.  Dans la page **Bienvenue dans la nouvelle règle de publication Web** , tapez un nom d’affichage pour la nouvelle règle de publication (par exemple, LyncDiscoveryURL).

4.  Dans la page **Sélectionner une action de règle** , sélectionnez **autoriser**.

5.  Dans la page **type de publication** , sélectionnez **publier un site Web ou un équilibrage de charge unique**.

6.  Dans la page sécurité de la **connexion au serveur** , sélectionnez **utiliser SSL pour se connecter au serveur Web publié ou à la batterie de**serveurs.

7.  Dans la page Détails de la **publication interne** , dans **nom du site interne**, tapez le nom de domaine complet (FQDN) de votre pool de répertoires (par exemple, lyncdir01. contoso. local). Si vous créez une règle pour l’URL des services Web externes sur le pool frontal, tapez l’adresse VIP de l’équilibrage de charge matérielle (HLB) en face du pool frontal.

8.  Dans la page Détails de la **publication interne** , dans **Path (facultatif)**, tapez ** / ** le chemin d’accès du dossier à publier, puis sélectionnez **transférer l’en-tête d’hôte d’origine**.

9.  Dans la page **Détails du nom public** , procédez comme suit:
    
      - Sous **accepter les demandes pour**, sélectionnez **ce nom de domaine**.
    
      - Dans **nom public**, tapez **lyncdiscover.** \<SIPDOMAIN\> (URL du service de découverte automatique externe). Si vous créez une règle pour l’URL des services Web externes sur le pool frontal, tapez le nom de domaine complet (FQDN) pour les services Web externes dans votre liste frontale (par exemple, lyncwebextpool01.contoso.com).
    
      - Dans **path**, tapez ** / **.

10. Dans la page **Sélectionner** un écouteur Web, dans **écouteur Web**, sélectionnez votre écouteur SSL existant avec le certificat public mis à jour.

11. Dans la page **délégation d’authentification** , sélectionnez **aucune délégation, mais le client pourra s’authentifier directement**.

12. Dans la page **jeu d’utilisateurs** , sélectionnez tous les **utilisateurs**.

13. Dans la page **fin de l’Assistant Nouvelle règle de publication Web** , vérifiez que les paramètres de règle de publication Web sont corrects, puis cliquez sur **Terminer**.

14. Dans la liste de règles de publication Web de Forefront TMG, double-cliquez sur la nouvelle règle que vous venez d’ajouter pour ouvrir les **Propriétés**.

15. Dans l’onglet **à** , procédez comme suit:
    
      - Sélectionnez **transférer l’en-tête d’hôte d’origine au lieu du premier**.
    
      - **Les demandes de sélection semblent provenir de l’ordinateur Forefront TMG**.

16. Dans l’onglet **pontage** , configurez les éléments suivants:
    
      - Sélectionnez **serveur Web**.
    
      - Sélectionnez **Rediriger les demandes vers le port http**et tapez **8080** pour le numéro de port.
    
      - Sélectionnez **Rediriger les demandes vers le port SSL**et tapez **4443** pour le numéro de port.

17. Cliquez sur **OK**.

18. Cliquez sur **appliquer** dans le volet Détails pour enregistrer les modifications et mettre à jour la configuration.

19. Cliquez sur **règle de test** pour vérifier que la configuration de votre nouvelle règle est correcte.

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a>Pour modifier une règle de publication sur le Web existante pour ajouter le SAN de découverte automatique et l’URL externes

1.  Cliquez sur **Démarrer**, pointez sur **programmes**, sur **Microsoft Forefront TMG**, puis cliquez sur gestion de **Forefront TMG**.
    
    <div>
    

    > [!IMPORTANT]  
    > Vous devrez répéter la modification pour chaque règle de publication et votre écouteur. En règle générale, il s’agit d’une règle et d’un écouteur pour les pools frontaux et l’un pour les directeurs ou pools de directeurs facultatifs, si vous les avez déployés.

    
    </div>

2.  Dans le volet gauche, développez **NomServeur**, cliquez avec le bouton droit sur **stratégie de pare-feu**, puis cliquez sur la règle applicable. Sous l’onglet **tâches** , cliquez sur **modifier la règle sélectionnée**.

3.  Dans l’onglet **nom du public** , dans **cette règle**, sélectionnez **demandes pour les sites Web suivants**.

4.  Cliquez sur **Ajouter**, tapez le nom du nouveau site de découverte automatique (par exemple, «lyncdiscover.contoso.com»), puis cliquez sur **OK**.

5.  Dans l' **** onglet écouteur, cliquez sur **Sélectionner un certificat** et attribuez le nouveau certificat aux entrées du réseau de découverte automatique ajoutées. Fermez les propriétés Listener et de publication Web.

6.  Cliquez sur **appliquer** dans le volet Détails pour enregistrer les modifications et mettre à jour la configuration.

7.  Cliquez sur **règle de test** pour vérifier que la configuration de votre nouvelle règle est correcte.

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a>Pour créer une règle de publication Web pour le port 80

1.  Cliquez sur **Démarrer**, pointez sur **programmes**, sur **Microsoft Forefront TMG**, puis cliquez sur gestion de **Forefront TMG**.

2.  Dans le volet gauche, développez **NomServeur**, cliquez avec le bouton droit sur **stratégie de pare-feu**, pointez sur **nouveau**, puis cliquez sur règle de **publication de site Web**.

3.  Dans la page **Bienvenue dans la nouvelle règle de publication Web** , tapez un nom d’affichage pour la nouvelle règle de publication (par exemple, la découverte automatique LYNC (http)).

4.  Dans la page **Sélectionner une action de règle** , sélectionnez **autoriser**.

5.  Dans la page **type de publication** , sélectionnez **publier un site Web ou un équilibrage de charge unique**.

6.  Dans la page sécurité de la **connexion au serveur** , sélectionnez utiliser des **connexions non sécurisées pour la connexion au serveur Web publié ou à la batterie de serveurs**.

7.  Dans la page Détails de la **publication interne** , dans **nom du site interne**, tapez l’adresse VIP de l’équilibrage de charge matérielle (HLB) en face du pool frontal.

8.  Dans la page Détails de la **publication interne** , dans **Path (facultatif)**, tapez ** / ** le chemin d’accès du dossier à publier, puis sélectionnez **transférer l’en-tête d’hôte d’origine au lieu de celle spécifiée dans le champ nom du site interne. **.

9.  Dans la page **Détails du nom public** , procédez comme suit:
    
      - Sous **accepter les demandes pour**, sélectionnez **ce nom de domaine**.
    
      - Dans **nom public**, tapez **lyncdiscover.** \<SIPDOMAIN\> (URL du service de découverte automatique externe).
    
      - Dans **path**, tapez ** / **.

10. Dans la page **Sélectionner** un écouteur Web, dans **écouteur Web**, sélectionnez un écouteur Web ou utilisez l’Assistant Nouvelle définition de l’écouteur Web pour en créer un autre.

11. Dans la page **délégation d’authentification** , sélectionnez **aucune délégation, et le client ne peut pas s’authentifier directement**.

12. Dans la page **jeu d’utilisateurs** , sélectionnez tous les **utilisateurs**.

13. Dans la page **fin de l’Assistant Nouvelle règle de publication Web** , vérifiez que les paramètres de règle de publication Web sont corrects, puis cliquez sur **Terminer**.

14. Dans la liste de règles de publication Web de Forefront TMG, double-cliquez sur la nouvelle règle que vous venez d’ajouter pour ouvrir les **Propriétés**.

15. Dans l’onglet **pontage** , configurez les éléments suivants:
    
      - Sélectionnez **serveur Web**.
    
      - Sélectionnez **Rediriger les demandes vers le port http**et tapez **8080** pour le numéro de port.
    
      - Vérifiez que l’option rediriger les **demandes vers le port SSL** n’est pas sélectionnée.

16. Cliquez sur **OK**.

17. Cliquez sur **appliquer** dans le volet Détails pour enregistrer les modifications et mettre à jour la configuration.

18. Cliquez sur **règle de test** pour vérifier que la configuration de votre nouvelle règle est correcte.

19. Vérifiez que l’URL du service de découverte automatique externe n’est pas définie sur une autre règle de publication Web.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration des serveurs proxy inverses pour Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md)  
[Exigences techniques pour la mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

