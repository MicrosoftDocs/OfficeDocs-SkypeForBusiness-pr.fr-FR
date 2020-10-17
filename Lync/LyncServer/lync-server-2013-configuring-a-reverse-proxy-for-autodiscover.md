---
title: 'Lync Server 2013 : configuration d’un proxy inverse pour la découverte automatique'
description: 'Lync Server 2013 : configuration d’un proxy inverse pour la découverte automatique.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a reverse proxy for Autodiscover
ms:assetid: 1e3c3cc2-fe55-408b-99c4-c6e0a9252689
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945619(v=OCS.15)
ms:contentKeyID: 51541456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f7873df063c526b4e51678ded02ca11d27c5e01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553950"
---
# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a>Configuration d’un proxy inverse pour la découverte automatique dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-12-12_

Découverte automatique et prise en charge des clients à l’aide de la découverte automatique nécessite la modification d’une règle de publication Web existante ou la création d’une nouvelle règle de publication Web pour le proxy inverse. La modification ou la création d’une nouvelle règle de publication n’est pas tributaire de la décision de mettre à jour ou de ne pas mettre à jour les listes d’autres noms de sujet sur les certificats de proxy inverse.

Si vous décidez d’utiliser le protocole HTTPs pour les demandes de service de découverte automatique Lync Server 2013 initiales et de mettre à jour les listes des autres noms du sujet sur les certificats de proxy inverse, vous devez affecter le certificat public mis à jour à l’écouteur SSL (Secure Sockets Layer) de votre proxy inverse. La mise à jour requise du certificat externe (public) inclut l’entrée de l’autre nom de sujet (SAN) pour lyncdiscover. \<domain name\> . Vous devez ensuite modifier l’écouteur existant pour les services Web externes ou créer une nouvelle règle de publication Web pour l’URL du service de découverte automatique externe, par exemple **lyncdiscover.contoso.com**. Si vous n’avez pas encore de règle de publication Web pour l’URL de services Web Lync Server 2013 externe pour votre pool frontal et votre pool directeur (si vous avez déployé des directeurs), vous devez également publier une règle pour cela.

<div>


> [!NOTE]  
> La règle de publication et l’écouteur du proxy inverse peuvent être utilisés par les services web externes et le service de découverte automatique, à condition que le certificat assigné à l’écouteur contienne le nom de sujet et les autres noms de sujet nécessaires aux deux. Pour plus d’informations sur la configuration par défaut du port d’écoute Web et de la règle de publication, voir <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up Reverse Proxy Servers for Lync Server 2013</A> pour plus d’informations.



</div>

Si vous décidez d’utiliser HTTP pour les demandes initiales du service de découverte automatique pour ne pas avoir à mettre à jour les autres noms de sujet pour le proxy inverse, vous devez créer ou modifier une règle de publication web pour le port 80.

Les procédures de cette section indiquent comment créer ou modifier les règles de publication web dans Microsoft Forefront Threat Management Gateway 2010 pour la découverte automatique.

<div>


> [!NOTE]  
> Ces procédures supposent que vous avez installé la version Standard Edition de Forefront Threat Management Gateway (TMG) 2010. Si vous utilisez un autre proxy inverse, les procédures, bien qu’identiques, devront être adaptées en tenant compte de la documentation du produit tiers.



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Pour créer une règle de publication web pour l’URL de découverte automatique externe

1.  Cliquez sur **Démarrer**, pointez sur **Programmes**, pointez sur **Microsoft Forefront TMG**, puis cliquez sur **Forefront TMG Management**.

2.  Dans le volet de gauche, développez **NomServeur**, cliquez avec le bouton droit sur **Stratégie de pare-feu**, pointez sur **Nouveau**, puis cliquez sur **Règle de publication web**.

3.  Dans la page **Assistant Nouvelle règle de publication web**, entrez un nom convivial pour la nouvelle règle de publication (par exemple, LyncDiscoveryURL).

4.  Dans la page **Sélectionner l’action de la règle**, sélectionnez **Autoriser**.

5.  Dans la page **Type de publication**, sélectionnez **Publier un seul site web ou équilibreur de charge**.

6.  Dans la page **Sécurité de connexion serveur**, sélectionnez **Utiliser SSL pour se connecter au serveur web publié ou à la batterie de serveurs**.

7.  Sur la page **Détails de publication interne** , dans **nom de site interne**, tapez le nom de domaine complet (FQDN) de votre pool de directeurs (par exemple, lyncdir01. contoso. local). Si vous créez une règle pour l’URL des services Web externes sur le pool frontal, tapez le nom de domaine complet du pool frontal (par exemple, lyncpool01. contoso. local).

8.  Sur la page **Détails de publication interne** , dans **chemin (facultatif)**, tapez **/\*** comme chemin d’accès du dossier à publier, puis sélectionnez **transférer l’en-tête d’hôte d’origine**.

9.  Dans la page **Informations sur les noms publics**, procédez comme suit :
    
      - Sous **Accepter les demandes pour**, sélectionnez **Ce nom de domaine**.
    
      - Dans **nom public**, tapez **lyncdiscover.**\<sipdomain\> (URL du service de découverte automatique externe). Si vous créez une règle pour l’URL des services Web externes sur le pool frontal, tapez le nom de domaine complet (FQDN) des services Web externes sur votre pool frontal (par exemple, lyncwebextpool01.contoso.com).
    
      - Dans **chemin d’accès**, tapez **/\*** .

10. Dans la page **Sélectionner le port d’écoute**, dans **Port d’écoute web**, sélectionnez votre écouteur SSL existant avec le certificat public mis à jour.

11. Dans la page **Délégation de l’authentification**, sélectionnez **Aucune délégation, mais le client peut authentifier directement**.

12. Dans la page **Ensemble d’utilisateurs**, cliquez sur **Tous les utilisateurs**.

13. Dans la page **Fin de l’Assistant Nouvelle règle de publication web**, vérifiez que les paramètres de la règle de publication web sont corrects, puis cliquez sur **Terminer**.

14. Dans la liste Forefront TMG de règles de publication web, double-cliquez sur la nouvelle règle que vous venez d’ajouter pour ouvrir les **Propriétés**.

15. Sous l’onglet **À**, procédez comme suit :
    
      - Sélectionnez **Transmettre l’en-tête de l’hôte d’origine plutôt que l’en-tête réel**.
    
      - Sélectionnez **Les demandes semblent émaner de l’ordinateur Forefront TMG**.

16. Sous l’onglet **Pontage**, configurez ce qui suit :
    
      - Sélectionnez **Serveur web**.
    
      - Sélectionnez **Rediriger les demandes au port HTTP** et tapez **8080** comme numéro de port.
    
      - Sélectionnez **Rediriger les demandes au port SSL** et tapez **4443** comme numéro de port.

17. Cliquez sur **OK**.

18. Cliquez sur **Appliquer** dans le volet des détails pour enregistrer les modifications et mettre à jour la configuration.

19. Cliquez sur **Tester la règle** pour vérifier que votre nouvelle règle est configurée correctement.

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a>Pour modifier une règle de publication web existante afin d’ajouter l’autre nom de sujet et l’URL du service de découverte automatique externe

1.  Cliquez sur **Démarrer**, pointez sur **Programmes**, pointez sur **Microsoft Forefront TMG**, puis cliquez sur **Forefront TMG Management**.
    
    <div>
    

    > [!IMPORTANT]  
    > Vous devrez répéter la modification pour chaque règle de publication et chaque écouteur que vous possédez. En règle générale, il s’agit d’une règle et d’un écouteur pour les pools frontaux et un pour les directeurs ou pools directeurs facultatifs, si vous les avez déployés.

    
    </div>

2.  Dans le volet gauche, développez **NomServeur**, cliquez avec le bouton droit sur **Stratégie de pare-feu**, puis cliquez sur la règle applicable. Sous l’onglet **Tâches**, cliquez sur **Modifier la règle sélectionnée**.

3.  Sous l’onglet **Nom public**, dans **Cette règle s’applique à**, sélectionnez **Demandes pour les sites web suivants**.

4.  Cliquez sur **Ajouter**, tapez le nom du nouveau site de découverte automatique (par exemple, « lyncdiscover.contoso.com »), puis cliquez sur **OK**.

5.  Sous l’onglet **Écouteur**, cliquez sur **Sélectionner un certificat** et assignez le nouveau certificat avec les entrées d’autres noms de sujet ajoutées du service de découverte automatique. Fermez les propriétés d’écouteur et de publication web.

6.  Cliquez sur **Appliquer** dans le volet des détails pour enregistrer les modifications et mettre à jour la configuration.

7.  Cliquez sur **Tester la règle** pour vérifier que votre nouvelle règle est configurée correctement.

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a>Pour créer une règle de publication web pour le port 80

1.  Cliquez sur **Démarrer**, pointez sur **Programmes**, pointez sur **Microsoft Forefront TMG**, puis cliquez sur **Forefront TMG Management**.

2.  Dans le volet de gauche, développez **NomServeur**, cliquez avec le bouton droit sur **Stratégie de pare-feu**, pointez sur **Nouveau**, puis cliquez sur **Règle de publication web**.

3.  Dans la page **Assistant Nouvelle règle de publication web**, entrez un nom convivial pour la nouvelle règle de publication (par exemple, Lync Autodiscover (HTTP)).

4.  Dans la page **Sélectionner l’action de la règle**, sélectionnez **Autoriser**.

5.  Dans la page **Type de publication**, sélectionnez **Publier un seul site web ou équilibreur de charge**.

6.  Dans la page **Sécurité de connexion serveur**, sélectionnez **Utiliser des connexions non sécurisées pour se connecter au serveur web publié ou à la batterie de serveurs**.

7.  Sur la page **Détails de publication interne** , dans **nom de site interne**, tapez le nom de domaine complet des services Web internes pour votre pool frontal (par exemple, lyncpool01. contoso. local).

8.  Sur la page **Détails de publication interne** , dans **chemin d’accès (facultatif)**, tapez **/\*** comme chemin d’accès du dossier à publier, puis sélectionnez **transférer l’en-tête d’hôte d’origine au lieu de celui spécifié dans le champ nom de site interne**.

9.  Dans la page **Informations sur les noms publics**, procédez comme suit :
    
      - Sous **Accepter les demandes pour**, sélectionnez **Ce nom de domaine**.
    
      - Dans **nom public**, tapez **lyncdiscover.**\<sipdomain\> (URL du service de découverte automatique externe).
    
      - Dans **chemin d’accès**, tapez **/\*** .

10. Dans la page **Sélectionner un port d’écoute**, dans **Port d’écoute web**, sélectionnez un écouteur web ou utilisez l’Assistant Nouvelle définition d’écouteur web pour en créer un nouveau.

11. Dans la page **Délégation de l’authentification**, sélectionnez **Aucune délégation, et le client ne peut pas authentifier directement**.

12. Dans la page **Ensemble d’utilisateurs**, cliquez sur **Tous les utilisateurs**.

13. Dans la page **Fin de l’Assistant Nouvelle règle de publication web**, vérifiez que les paramètres de la règle de publication web sont corrects, puis cliquez sur **Terminer**.

14. Dans la liste Forefront TMG de règles de publication web, double-cliquez sur la nouvelle règle que vous venez d’ajouter pour ouvrir les **Propriétés**.

15. Sous l’onglet **Pontage**, configurez ce qui suit :
    
      - Sélectionnez **Serveur web**.
    
      - Sélectionnez **Rediriger les demandes au port HTTP** et tapez **8080** comme numéro de port.
    
      - Vérifiez que l’option **Rediriger les demandes au port SSL** n’est pas sélectionnée.

16. Cliquez sur **OK**.

17. Cliquez sur **Appliquer** dans le volet des détails pour enregistrer les modifications et mettre à jour la configuration.

18. Cliquez sur **Tester la règle** pour vérifier que votre nouvelle règle est configurée correctement.

19. Vérifiez que l’URL du service de découverte automatique externe n’est définie sur aucune autre règle de publication web.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration des serveurs proxy inverses pour Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

