@login_required(login_url='/')
def VIEW_COURSE(request):
    course = Course.objects.all()
    context = {
        'course':course,
    }
    return render(request,'Hod/view_course.html',context)

@login_required(login_url='/')
def EDIT_COURSE(request,id):
    course = Course.objects.get(id = id)


    context = {
        'course':course,
    }
    return render(request,'Hod/edit_course.html',context)

@login_required(login_url='/')
def UPDATE_COURSE(request):
    if request.method == "POST":
        name = request.POST.get('name')
        course_id = request.POST.get('course_id')


        course = Course.objects.get(id = course_id)
        course.name = name
        course.save()
        messages.success(request,'Course are successfully update')
        return redirect('view_course')

    return render(request,'Hod/edit_course.html')


@login_required(login_url='/')
def DELETE_COURSE(request,id):
    course = Course.objects.get(id = id)
    course.delete()
    messages.success(request,'Course are successfully deleted')

    return redirect('view_course')


@login_required(login_url='/')
def ADD_SUBJECT(request):
    course = Course.objects.all()

    if request.method =="POST":
        subject_name = request.POST.get('subject_name')
        course_id = request.POST.get('course_id')

        course = Course.objects.get(id = course_id)

        subject = Subject(
            name = subject_name,
            course = course,
        )

        subject.save()
        messages.success(request,'Subjects are successfully deleted')
        return redirect('add_subject')




    context = {
        'course':course,
    }

    return render(request,'Hod/add_subject.html',context)


@login_required(login_url='/')
def VIEW_SUBJECT(request):
    subject = Subject.objects.all()
    
    context={
        'subject':subject,
    }

    return render(request,'Hod/view_subject.html',context)



@login_required(login_url='/')
def EDIT_SUBJECT(request,id):
    subject = Subject.objects.get(id = id)
    course = Course.objects.all()

    context = {
        'subject':subject,
        'course':course,
    }


    return render(request,'Hod/edit_subject.html',context)
