---
title: "Lync Server 2013 : Conf. Lync Server 2013 pr fonct. mess. unif. sur MES"
TOCTitle: Configuration de Lync Server 2013 pour qu’il fonctionne avec la messagerie unifiée sur Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398193(v=OCS.15)
ms:contentKeyID: 49296287
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de Lync Server 2013 pour qu’il fonctionne avec la messagerie unifiée sur Microsoft Exchange Server

 

_**Dernière rubrique modifiée :** 2016-12-08_

Cette étape nécessite l’utilitaire d’intégration de la messagerie unifiée Exchange (OcsUmUtil.exe). Cet outil est disponible sur le serveur Lync Server 2013 dans le dossier ..\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Support.

## Exécution de l’utilitaire d’intégration de la messagerie unifiée Exchange

L’utilitaire d’intégration de la messagerie unifiée Exchange doit être exécuté à partir d’un compte d’utilisateur présentant les caractéristiques suivantes :

  - l’appartenance aux groupes RTCUniversalServerAdmins et RtcUniversalUserAdmins (comprenant l’autorisation de lecture des paramètres de la messagerie unifiée Exchange Server) ;

  - les droits d’utilisateurs dans le domaine pour la création d’objets contact dans le conteneur d’unités d’organisation spécifié.

Lorsque vous exécutez l’utilitaire d’intégration de la messagerie unifiée Exchange, il exécute les tâches suivantes :

  - Il créé des objets contact pour chaque numéro de standard automatique et numéro d’accès d’abonné dont les utilisateurs de Voix Entreprise se serviront.

  - Il vérifie que le nom de chaque plan de numérotation Voix Entreprise correspond au contexte téléphonique du plan de numérotation de messagerie unifiée correspondant. Cette correspondance est uniquement nécessaire si le plan de numérotation de messagerie unifiée fonctionne sur une version d’Exchange *antérieure* à Exchange 2010 Service Pack 1 (SP1).

> [!IMPORTANT]  
> Avant d’exécuter l’utilitaire d’intégration de messagerie unifiée Exchange, vous devez effectuer ce qui suit :<ul><li><p>Créez un ou plusieurs plans de numérotation de messagerie unifiée Exchange, comme il est indiqué dans la documentation du produit Exchange.
> Pour Microsoft Exchange Server 2010, reportez-vous à « Créer un plan de numérotation de messagerie unifiée » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>.
> Pour Microsoft Exchange Server 2007 Service Pack 1 (SP1), reportez-vous à « Procédure de création d’un plan de numérotation URI SIP de messagerie unifiée » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>.</p></li><li><p>Créez un ou plusieurs plans de numérotation Lync Server, comme il est indiqué dans <a href="lync-server-2013-create-a-dial-plan.md">Création d’un plan de numérotation dans Lync Server 2013</a>.</li>
> <ul><li>Si vous utilisez une version d’Exchange antérieure à Microsoft Exchange Server 2010 SP1, vous devez entrer le nom de domaine complet du plan de numérotation SIP de messagerie unifiée Exchange correspondant dans le champ <strong>Nom simple</strong> du plan de numérotation Lync Server 2013. Si vous utilisez Microsoft Exchange Server 2010 SP1 ou le tout dernier service pack, il n’est pas nécessaire que ces noms de plan de numérotation correspondent.</li><ul>
> <li>Créez un standard automatique et assurez-vous que le numéro d’accès abonné et le numéro du standard automatique sont au format E.164.</li></ul>


## Pour exécuter l’utilitaire d’intégration de la messagerie unifiée Exchange

1.  Sur un serveur frontal, ouvrez une invite de commandes, entrez **cd %CommonProgramFiles%\\Microsoft Lync Server 2013\\Support** , puis appuyez sur Entrée.

2.  Tapez **OcsUmUtil.exe** , puis appuyez sur Entrée.

3.  Cliquez sur **Charger les données** pour rechercher toutes les forêts Exchange approuvées.

4.  Dans la liste **Plans de numérotation SIP** , sélectionnez un plan de numérotation SIP de messagerie unifiée pour lequel vous souhaitez créer des objets contact, puis cliquez sur **Ajouter** .

5.  Dans la zone **Contact** , acceptez l’unité d’organisation par défaut, ou cliquez sur **Parcourir** pour démarrer le **Sélecteur d’unités d’organisation** . Dans la zone **Sélecteur d’unités d’organisation** , sélectionnez une unité d’organisation et cliquez sur **OK** . Vous pouvez aussi cliquer sur **Créer une unité d’organisation** pour créer une unité d’organisation sous la racine, ou toute autre unité d’organisation dans le domaine (par exemple, « OU=RTC Special Accounts,DC=fourthcoffee,DC=com »), puis cliquez sur **OK** .
    
    > [!NOTE]  
    > Le nom unique de l’unité d’organisation que vous avez sélectionnée ou créée est désormais affiché dans la zone <strong>Unité d’organisation</strong> .

6.  Dans la zone **Nom** , acceptez le nom de plan de numérotation par défaut, ou tapez un nouveau nom complet pour l’objet contact que vous créez.
    
    > [!NOTE]  
    > Par exemple, si vous créez un objet contact d’accès abonné, vous pouvez tout simplement le nommer Accès Abonné.

7.  Dans la zone **Adresse SIP** , acceptez l’adresse SIP par défaut ou tapez une nouvelle adresse SIP.
    
    > [!NOTE]  
    > Si vous tapez une nouvelle adresse SIP, elle doit commencer par <strong>SIP:</strong> (c’est-à-dire, « SIP: » le signe : compris).

8.  Dans la liste **Serveur ou pool** , sélectionnez le serveur Standard Edition ou le pool de serveurs frontaux sur lequel l’objet contact doit être activé.
    
    > [!NOTE]  
    > Il est préférable de choisir le pool où les utilisateurs activés pour Voix Entreprise et la messagerie unifiée Exchange sont déployés.

9.  Dans la liste **Numéro de téléphone** , sélectionnez **Entrez le numéro de téléphone** ou **Utilisez ce numéro pilote à partir d’Exchange UM** , puis entrez un numéro de téléphone.

10. Dans la liste **Type de contact** , sélectionnez le type de contact que vous souhaitez créer, puis cliquez sur **OK** .

11. Répétez les étapes 1 à 10 pour les objets contact supplémentaires que vous souhaitez créer.
    
    > [!NOTE]  
    > Vous devez créer au moins un contact pour chaque standard automatique. Si vous souhaitez un accès externe, vous devez également créer un contact d’accès abonné et spécifier des numéros SDA (Sélection directe à l’arrivée).

Pour vérifier que les objets contact ont bien été créés, ouvrez Utilisateurs et ordinateurs Active Directory et sélectionnez l’unité d’organisation dans laquelle les objets ont été créés. Les objets contact s’affichent dans le volet d’informations.

