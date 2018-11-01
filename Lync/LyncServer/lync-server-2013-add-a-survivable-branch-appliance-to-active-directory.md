---
title: 'Lync Server 2013 : Ajout d’un Survivable Branch Appliance à Active Directory'
TOCTitle: Ajout d’un Survivable Branch Appliance à Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425906(v=OCS.15)
ms:contentKeyID: 49296981
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ajout d’un Survivable Branch Appliance à Active Directory dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-23_

Si vous envisagez de déployer un Survivable Branch Appliance, vous devez ajouter le Survivable Branch Appliance aux services de domaine Active Directory. Cette procédure doit être effectuée sur le site central

> [!IMPORTANT]  
> et uniquement dans le cas d’un déploiement d’un Survivable Branch Appliance. N’effectuez pas cette procédure si vous déployez un serveur Survivable Branch Server.

## Pour ajouter un Survivable Branch Appliance aux services de domaine Active Directory

1.  Ouvrez une session sur un serveur membre, en tant que membre du groupe Administrateurs d’entreprise.

2.  Cliquez sur **Démarrer** , sur **Outils d’administration** , puis sur **Utilisateurs et ordinateurs Active Directory** .

3.  Dans le menu **Actions** , cliquez sur **Nouveau** , puis sur **Ordinateur** .

4.  Dans la boîte de dialogue **Nouvel objet - Ordinateur** , tapez le nom de l’objet ordinateur Survivable Branch Appliance (par exemple, SiteSuccursale1), puis cliquez sur **Modifier** .

5.  Dans la boîte de dialogue **Sélectionner un utilisateur ou un groupe** , ajoutez le groupe RTCUniversalSBATechnicians, puis cliquez sur **OK** .
    
    > [!NOTE]  
    > Un membre du groupe RTCUniversalSBATechnicians sur le site de succursale ajoutera ce périphérique au domaine plus tard.

6.  Cliquez sur **OK** pour enregistrer l’objet ordinateur Survivable Branch Appliance.

7.  Cliquez sur **Démarrer** , sur **Outils d’administration** , puis sur **Modification ADSI** .

8.  Dans **Modification ADSI** , cliquez avec le bouton droit sur l’objet ordinateur que vous avez créé au cours des étapes précédentes, puis cliquez sur **Propriétés** .

9.  Dans la liste d’attributs, cliquez sur **servicePrincipalName** , puis sur **Modifier** .

10. Dans le champ **Valeur à ajouter** , tapez HÔTE/\<NOM DOMAINE COMPLET SBA\> où \<NOM DOMAINE COMPLET SBA\> correspond au nom de domaine complet (FQDN) de votre Survivable Branch Appliance. Par exemple, tapez **HOST/SiteSuccursale1.contoso.com** .

11. Cliquez sur **OK** pour enregistrer le paramètre d’attribut **servicePrincipalName** , puis cliquez sur **OK** pour enregistrer les propriétés de l’objet ordinateur.

12. Dans **Utilisateurs et ordinateurs Active Directory** , cliquez avec le bouton droit sur **Utilisateurs** , cliquez sur **Nouveau** , puis sur **Utilisateur** .

13. Entrez les informations dans l’Assistant pour créer un compte d’utilisateur de domaine pour un technicien Survivable Branch Appliance.

14. Dans **Utilisateurs et ordinateurs Active Directory** , cliquez sur **Utilisateurs** , cliquez avec le bouton droit de la souris sur l’objet utilisateur, puis sur **Ajouter à un groupe** .

15. Dans **Entrez les noms d’objets à sélectionner** , tapez **RTCUniversalSBATechnicians** , puis cliquez sur **OK** .

16. Répétez les étapes 12 à 15 pour chaque technicien de site de succursale.

**Étape suivante** : [Ajout des sites de succursale à votre topologie dans Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

