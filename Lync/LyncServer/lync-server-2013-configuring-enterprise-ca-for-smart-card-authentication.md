---
title: "Conf. d’une autorité de cert. d’entreprise pour l’auth. par carte à puce"
TOCtitle: "Conf. d’une autorité de cert. d’entreprise pour l’auth. par carte à puce"
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn308571(v=OCS.15)
ms:contentKeyID: 56269649
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration d’une autorité de certification d’entreprise pour l’authentification par carte à puce

 

_**Dernière rubrique modifiée :** 2016-12-08_

La section suivante décrit la configuration d’une autorité de certification d’entreprise pour prendre en charge l’authentification par carte à puce. Pour plus d’informations sur l’installation d’une autorité de certification racine d’entreprise, voir la rubrique « Installer une autorité de certification racine d’entreprise » à l’adresse [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364).

## Configuration d’une autorité de certification racine d’entreprise pour prendre en charge l’authentification par carte à puce

Les étapes suivantes décrivent la configuration d’une autorité de certification racine d’entreprise pour prendre en charge l’authentification par carte à puce :

1.  Connectez-vous à l’ordinateur autorité de certification racine d’entreprise à l’aide d’un compte d’administrateur de domaine.

2.  Démarrer le Gestionnaire système, puis vérifiez que le rôle Inscription de l’autorité de certification via le web est installé.

3.  Dans le menu **Outils d’administration**, ouvrez la console de gestion **Autorité de certification**.

4.  Dans le volet de navigation, développez **Autorité de certification**.

5.  Cliquez avec le bouton droit sur **Modèles de certificat**, sélectionnez **Nouveau**, puis **Modèle de certificat à délivrer**.

6.  Sélectionnez **Agent d’inscription**, **Utilisateur de carte à puce** et **Connexion par carte à puce**.

7.  Cliquez sur **OK**.

8.  Cliquez avec le bouton droit sur **Modèles de certificat**.

9.  Sélectionnez **Gérer**.

10. Ouvrez les propriétés du modèle utilisateur de carte à puce.

11. Cliquez sur l’onglet **Sécurité**.

12. Modifiez les autorisations comme suit :
    
      - Ajoutez des comptes AD d’utilisateurs individuels avec les autorisations Lire/Inscrire (Autoriser) ou
    
      - Ajoutez un groupe de sécurité contenant des utilisateurs de carte à puce avec les autorisations Lire/Inscrire (Autoriser) ou
    
      - Ajoutez le groupe Utilisateurs du domaine avec les autorisations Lire/Inscrire (Autoriser).

